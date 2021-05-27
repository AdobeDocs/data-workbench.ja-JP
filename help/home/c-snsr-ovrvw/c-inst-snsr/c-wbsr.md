---
description: AIX 5.1以降で実行するWebSphere 5.x用Sensorのインストールと設定に関する詳細な手順。
title: WebSphere（AIX）
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
exl-id: e560d265-dc84-4ff2-ac86-7a2ac5261451
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 1%

---

# WebSphere（AIX）{#websphere-on-aix}

AIX 5.1以降で実行するWebSphere 5.x用Sensorのインストールと設定に関する詳細な手順。

[!DNL Sensor]用のプログラムファイルは、Adobeダウンロードサイトから取得したインストールファイルにパッケージ化されます。 ご使用のWebサーバーの[!DNL Sensor]インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード(またはAdobe担当者から入手)してください。

>[!NOTE]
>
>WebSphereサーバーの[!DNL Sensor]は、対照実験をサポートしていません。 対照実験について詳しくは、『*Data Workbench対照実験ガイド』を参照してください。*

## プログラムファイル{#section-86f69127278c41bc90b97b68bb40bc6e}をインストールします。

Sensorのプログラムファイルを抽出し、サーバーマシンにインストールする手順。

1. rootユーザーまたはroot権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し解凍します。

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. 展開済みのプログラム・ファイルを、次の表に示すディレクトリにコピーします。

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
   <td colname="col2"> コレクタ負荷モジュール </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> コレクターロードモジュールライブラリ </td> 
   <td colname="col3"> WebSphere /libディレクトリ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> 送信機プログラム </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書を検証するために使用される証明書 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、 TestExperiment.xlsというスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorが実行されているマシンにファイルをインストールする必要はありません（ただし、インストールする場合もあります）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight対照実験ガイド』を参照してください。

**プログラムファイルに対するアクセス許可**

プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。

この節で説明した権限が正確に設定されていることを確認してください。

デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクなし）される場合があります。

権限を推奨されるデフォルト設定にリセットするには、以下のchmodコマンドを使用します。

>[!NOTE]
>
>ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| ファイル | デフォルトの権限 | chmodコマンド |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw-rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

推奨されるデフォルト以外の権限を使用する場合は、「 Sensor UNIX File Permissions 」の情報を確認し、これらのファイルの使用方法を必ず理解してください。

## センサー設定ファイル{#section-283c8a92fa8841c1b6034e5f834ef4e7}を編集します。

txlogd.confファイルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、ディスクキューのサイズ、Insightサーバーのアドレス、このセンサーで生成されるデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションパラメーターが含まれています。

* 必須のパラメーターは、Sensorをインストールする際に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に動作しません。
* オプションのパラメーターは、事前定義済みの値（変更可能）をデフォルトとして設定するか、オプション機能を有効にする設定です。

**設定ファイルを編集するには**

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションパラメーターを設定します。
1. ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-63285a2328604f20a2cb31b3d5cb80e6}

txlogd.confファイルを設定した後のディスクキューの作成手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクターモジュールとトランスミッタープログラムの両方に、ファイルへの読み取り/書き込みアクセス権が付与されていることを確認します。

1. センサーがインストールされているコンピューターで、次のコマンドを実行してトランスミッターを起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッターをインタラクティブモードで起動します。 このモードでは、トランスミッターメッセージが画面に表示され、キーボードコマンドを使用してトランスミッターを操作することもできます。
   * 「c」オプションは、トランスミッターにディスクキューを作成するよう指示します。
   * 「f」オプションは、設定ファイルの場所を指定します。

1. トランスミッターが、QueueFileパラメーターで指定された場所とQueueSizeパラメーターで指定されたサイズでディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押してトランスミッターを終了し、次の操作を行います。

   1. txtlogd.confファイルを調べ、QueueFileおよびQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSizeパラメータで指定されたサイズのファイルを保持するのに十分な領域があることを確認します。
   1. 必要な修正を行い、この手順を繰り返します。

## Webアプリケーションにコレクターを追加します。 {#section-d17297b1193f4e3cb150fb41f754ef12}

WebSphereサーバーの場合、コレクターはサーブレットコンテナ内でフィルターとして動作します。

Webアプリケーションにコレクターを追加するには、Webアプリケーションのweb.xmlデプロイメント記述子にフィルターを追加し、Webアプリケーションを再起動します。

1. テキストエディターを使用して、SensorがイベントをキャプチャするWebサーバーのweb.xmlファイルを開きます。
1. 次の`<filter>`要素と`<filter-mapping>`要素を記述子ファイルに追加します。 /etcディレクトリにtxlogd.confをインストールしなかった場合は、`<param-value>`要素にこのファイルへの正しいパスを入力する必要があります。

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

1. Webアプリケーションを再起動します。 コレクターはアプリケーションと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始します。

## コレクターと共有オブジェクトファイルの場所を宣言{#section-e641f08999d34a648aaee2111b69ca25}

Websphere起動スクリプトを編集し、J2EECollector.jarおよびlibvisual_sciences.soファイルの場所を宣言する手順。

1. Websphere /binディレクトリのsetupCmdLine.shファイルを開きます。
1. $WAS_CLASSPATH変数を定義する行の後に、次の行を追加します。

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. $WAS_LIBPATH変数を定義するcaseブロックの後に、次の行を追加します。

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. [!DNL setupCmdLine.sh]ファイルを保存します。

## センサー{#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}をテストします。

トランスミッターを起動し、Insightサーバーに接続してイベントデータを送信できることを確認する手順です。

>[!NOTE]
>
>トランスミッターがイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッターがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上で）ブラウザーを開き、センサーが動作しているWebサーバーからページを要求します（センサーが監視しているページを必ず選択してください）。
1. リクエストを発行した後、トランスミッターのコンソールで、ターゲットInsightサーバーにイベントデータを送信していることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次の点を確認します。

   * ターゲットInsightサーバーが実行中です。
   * ServerAddressパラメーターとServerPortパラメーターは、 txtlogd.confで正しく設定されています。 サーバー名を使用してServerAddressを指定した場合は、代わりに数値IPアドレスを使用してみてください。
   * CertNameパラメーターの値は、ターゲットInsightサーバーのデジタル証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへのトランスミッターの追加{#section-23bb905100d04f018af93873dd4d5f68}

Webサーバーマシンを再起動したときにトランスミッターが自動的に読み込まれるようにする情報です。

システム起動スクリプトに、次のコマンド（トランスミッターを起動）を追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、トランスミッターをデーモンとして起動します。 トランスミッターが生成する動作メッセージとエラーメッセージは、syslogに書き込まれます。

## 追加データのキャプチャ{#section-d5ccf8ee50914a87938e0c17480757e6}

すべてのプラットフォームのセンサーは、HTTPリクエストヘッダーと応答ヘッダーで使用可能なデータを収集できます。

J2EEプラットフォームのセンサーは、他のプラットフォームでは利用できないデータを収集するメカニズムを提供します。 J2EEプラットフォーム（J2EEコレクター）のコレクターは、アプリケーションレイヤー上に配置され、アプリケーションでのみ使用可能で、ページタグ付けやヘッダーで公開されない機密データを収集できます。

>[!NOTE]
>
>ページタグやヘッダーの変更によってデータが非表示になる場合でも、ページのソースコードを調べたり、ブラウザープラグインツールを使用してヘッダーを調べたりするユーザーは引き続き使用できます。

例えば、J2EEコレクターを使用して、ページに表示されるリンクのコストパークリック(CPC)データ、ページ上の機密パートナー情報、その他多くのデータポイントを取り込むことができます。 J2EE環境を使用すると、Webアプリを変更して、アドビのコレクタークラスを使用してこのカスタムデータを簡単に取り込むことができます。

J2EEプラットフォームのセンサーがリクエストを受け取ると、appendToLog関数をインポートするコレクタークラスを呼び出します。 appendToLog関数は、 appendToLog関数で指定されたクエリー文字列パラメーターを最初のリクエストに追加します。 これにより、最初のリクエストのURIに、取り込むデータの名前と値に対応する追加のクエリー文字列の名前と値のペアが含まれます。 例えば、特定の広告配置またはクリックスルーリンクの値が20セントの場合、CPC=20が最初の要求に追加されます。 Insightサーバーは、これらの値をデータセットに処理して分析します。 この収集手法のもう1つのメリットは、ページタグ付け手法を使用して作成されるのと同様に、追加のログエントリを作成せずに追加のデータを収集できる点です。

処理について詳しくは、『データセット設定ガイド&#x200B;*』を参照してください。*

1. データの取り込み元の.jspページの先頭に次のコードを追加します。

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. コレクターオブジェクトのappendToLog()メソッドを使用して、要求された.jspページのクエリー文字列に目的の名前と値のペアを追加します。 次の例では、/index.jspページに対して要求された.jspページのクエリー文字列に「A=1」と「B=2」を追加します。

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

   結果のリクエストURIは/index.jsp?A=1&amp;B=2です。

1. 追加データを取り込む.jspページごとに、この手順を繰り返します。
