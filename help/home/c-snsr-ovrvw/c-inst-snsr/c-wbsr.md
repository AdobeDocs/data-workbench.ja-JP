---
description: AIX 5.1 以降で実行する WebSphere 5.x 用 Sensor のインストールと設定に関する詳細な手順。
title: WebSphere（AIX）
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 1%

---

# WebSphere（AIX）{#websphere-on-aix}

{{eol}}

AIX 5.1 以降で実行する WebSphere 5.x 用 Sensor のインストールと設定に関する詳細な手順。

用のプログラムファイル [!DNL Sensor] は、インストールのダウンロードサイトから取得したAdobeファイルにパッケージ化されます。 まだ [!DNL Sensor] 次の手順を開始する前に、お使いの Web サーバー用のインストールファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

>[!NOTE]
>
>この [!DNL Sensor] WebSphere サーバーの場合は、対照実験はサポートされていません。 対照実験について詳しくは、 *Data Workbench対照実験ガイド。*

## プログラムファイルのインストール {#section-86f69127278c41bc90b97b68bb40bc6e}

Sensorto 用のプログラムファイルを抽出してサーバーマシンにインストールする手順です。

1. root ユーザーまたは root 権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. 展開済みのプログラムファイルを、次の表で指定されたディレクトリにコピーします。

<table id="table_0E3B403071EF44AFBF0DD673EFEBBFE5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ターゲットディレクトリ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> コレクターロードモジュール </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> コレクターロードモジュールライブラリ </td> 
   <td colname="col3"> WebSphere /lib ディレクトリ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> 送信機プログラム </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor 設定ファイル </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中に Insight サーバーが提示する電子証明書を検証するために使用される証明書 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestExperiment.xls という名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールを選択することもできます）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

**プログラムファイルに対する権限**

プログラムファイルに対する権限が正しくないと、Sensor のインストール時に発生する問題の大部分が発生します。

権限は、この節で説明したとおりに設定してください。

デフォルトでは、tar ファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクなし）される場合があります。

権限を推奨されるデフォルト設定にリセットするには、次の chmod コマンドを使用します。

>[!NOTE]
>
>ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| ファイル | デフォルトの権限 | chmod コマンド |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw-rw-r-— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw-r-— | chmod 664 |
| trust_ca_cert.pem | rw-rw-r-— | chmod 664 |

推奨されるデフォルト以外の権限を使用する場合は、Sensor UNIX ファイルの権限に関する情報を確認し、これらのファイルの使用方法を理解してください。

## Sensor 設定ファイルを編集します。 {#section-283c8a92fa8841c1b6034e5f834ef4e7}

txlogd.conf ファイルには、Sensor の設定パラメーターが含まれています。

ファイルを編集して、ディスクキューのサイズ、Insight サーバーのアドレス、このセンサーによって生成されるデータに添付される ID を指定する必要があります。

設定ファイルには、必須のパラメーターとオプションのパラメーターが含まれています。

* 必須パラメータは、Sensor をインストールする際に指定する必要がある設定です。 これらの設定がないと、センサーは正常に動作しません。
* オプションのパラメーターは、事前定義済みの値（変更可能）をデフォルトにする設定またはオプション機能を有効にする設定です。

**設定ファイルを編集するには**

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションパラメーターを設定します。
1. ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-63285a2328604f20a2cb31b3d5cb80e6}

txlogd.conf ファイルを設定した後のディスクキューの作成手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクターモジュールとトランスミッタープログラムの両方に、ファイルへの読み取り/書き込みアクセス権が付与されていることを確認します。

1. センサーがインストールされているコンピューターで、次のコマンドを実行してトランスミッターを起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッターをインタラクティブモードで開始します。 このモードでは、トランスミッターメッセージを画面に表示し、キーボードコマンドを使用してトランスミッターを操作できます。
   * 「c」オプションは、トランスミッターにディスクキューを作成するよう指示します。
   * 「f」オプションは、設定ファイルの場所を指定します。

1. トランスミッターが、QueueFile パラメーターで指定された場所と、QueueSize パラメーターで指定されたサイズにディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl+C キーを押してトランスミッターを終了し、次の手順を実行します。

   1. txtlogd.conf ファイルを調べ、QueueFile および QueueSize パラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSize パラメータで指定されたサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Web アプリケーションにコレクタを追加 {#section-d17297b1193f4e3cb150fb41f754ef12}

WebSphere サーバーの場合、コレクターはサーブレットコンテナ内でフィルターとして動作します。

Web アプリケーションにコレクターを追加するには、Web アプリケーションの web.xml デプロイメント記述子にフィルターを追加し、Web アプリケーションを再起動します。

1. テキストエディターを使用して、Sensor が取り込むイベントの Web サーバーの web.xml ファイルを開きます。
1. 以下を追加します。 `<filter>` および `<filter-mapping>` 記述子ファイルの要素。 /etc ディレクトリに txlogd.conf をインストールしなかった場合は、 `<param-value>` 要素。

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping>
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping>
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Web アプリケーションを再起動します。 コレクターがアプリケーションと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みが開始されます。

## コレクターと共有オブジェクトファイルの場所を宣言する {#section-e641f08999d34a648aaee2111b69ca25}

Websphere 起動スクリプトを編集し、J2EECollector.jar および libvisual_sciences.so ファイルの場所を宣言する手順です。

1. Websphere /bin ディレクトリの setupCmdLine.sh ファイルを開きます。
1. $WAS_CLASSPATH 変数を定義する行の後に、次の行を追加します。

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. $WAS_LIBPATH 変数を定義する case ブロックの後に、次の行を追加します。

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. 保存する [!DNL setupCmdLine.sh] ファイル。

## センサーをテストする {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

トランスミッターを起動し、Insight サーバーに接続してイベントデータを送信できることを確認する手順です。

>[!NOTE]
>
>トランスミッターが Insight サーバーにイベントデータを正常に送信できることを確認するには、次のテストを開始する前に、ターゲット Insight サーバーがインストールされ、実行されていることを確認してください。

1. トランスミッターがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上で）ブラウザーを開き、センサーが動作している Web サーバーからページをリクエストします（センサーが監視しているページを必ず選択してください）。
1. リクエストを発行した後、トランスミッターのコンソールを調べて、イベントデータがターゲット Insight サーバーに送信されていることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次の点を確認します。

   * ターゲット Insight サーバーが実行中です。
   * txtlogd.conf で ServerAddress および ServerPort パラメーターが正しく設定されている。 サーバー名を使用して ServerAddress を指定した場合は、代わりに数値の IP アドレスを使用してみてください。
   * CertName パラメーターの値は、ターゲット Insight サーバーの電子証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへのトランスミッターの追加 {#section-23bb905100d04f018af93873dd4d5f68}

Web サーバーマシンを再起動したときに、トランスミッターが自動的に読み込まれるようにする情報です。

次のコマンド（トランスミッターを起動する）をシステム起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、トランスミッターをデーモンとして起動します。 トランスミッタが生成する動作およびエラーメッセージは、syslog に書き込まれます。

## 追加データのキャプチャ {#section-d5ccf8ee50914a87938e0c17480757e6}

すべてのプラットフォームのセンサーは、HTTP リクエストヘッダーと応答ヘッダーで使用可能な任意のデータを収集できます。

J2EE プラットフォーム用のセンサーは、他のプラットフォームでは利用できないデータを収集するメカニズムを提供します。 J2EE プラットフォーム（J2EE コレクター）のコレクターは、アプリケーションレイヤー上に配置され、アプリケーションでのみ使用可能で、ページタグ付けやヘッダーで公開されない機密データを収集できます。

>[!NOTE]
>
>ページタグやヘッダーの変更によってデータが非表示になる場合がありますが、ページのソースコードを調べたり、ブラウザープラグインツールを使用してヘッダーを確認したりするユーザーは引き続き使用できます。

例えば、J2EE コレクターを使用して、ページに表示されるリンクのクリック単価 (CPC) データや、ページ上の機密パートナー情報、その他多くのデータポイントを取り込むことができます。 J2EE 環境を使用すると、Web アプリを変更して、アドビのコレクタークラスを使用してこのカスタムデータを簡単に取り込むことができます。

J2EE プラットフォームのセンサーがリクエストを受け取ると、appendToLog 関数を読み込むコレクタークラスを呼び出します。 appendToLog 関数は、最初のリクエストに appendToLog 関数で指定されたクエリー文字列パラメーターを追加します。 これにより、取り込まれるデータの名前と値に対応する追加のクエリー文字列の名前と値のペアを含む最初のリクエストの URI が生成されます。 例えば、特定の広告配置またはクリックスルーリンクの値が 20 セントの場合、CPC=20 が初期リクエストに追加されます。 Insight サーバーは、これらの値を分析用にデータセットに処理します。 この収集方法のもう 1 つの利点の 1 つは、ページのタグ付け手法を使用して作成されるように、追加のログエントリを作成せずに追加のデータを収集できる点です。

処理について詳しくは、 *データセット設定ガイド*.

1. データの取り込み元の.jsp ページの先頭に次のコードを追加します。

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. collector オブジェクトの appendToLog() メソッドを使用して、要求された.jsp ページのクエリ文字列に必要な名前と値のペアを追加します。 次の例では、/index.jspページに対して要求された.jsp ページのクエリー文字列に&quot;A=1&quot;と&quot;B=2&quot;を追加します。

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   結果のリクエスト URI は/index.jsp?A=1&amp;B=2 です。

1. 追加のデータを取り込む.jsp ページごとに、この手順を繰り返します。
