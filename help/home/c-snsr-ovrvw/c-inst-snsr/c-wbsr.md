---
description: AIX 5.1以降で実行するWebSphere 5.x用Sensorのインストールおよび設定の詳細な手順。
solution: Analytics
title: WebSphere（AIX）
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1645'
ht-degree: 1%

---


# WebSphere（AIX）{#websphere-on-aix}

AIX 5.1以降で実行するWebSphere 5.x用Sensorのインストールおよび設定の詳細な手順。

のプログラムファイル [!DNL Sensor] は、Adobeのダウンロードサイトから取得したインストールファイルにパッケージ化されます。 お使いのWebサーバーの [!DNL Sensor] インストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード(またはAdobeの担当者から入手)してください。

>[!NOTE]
>
>WebSphereサーバ [!DNL Sensor] ー用は、対照実験をサポートしていません。 対照実験の詳細については、『 *Data Workbench制御実験ガイド』を参照してください。*

## Install the Program Files {#section-86f69127278c41bc90b97b68bb40bc6e}

Sensorのプログラムファイルを抽出し、サーバーマシンにインストールする手順です。

1. rootユーザーまたはroot権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   ```
   gunzip installationFilename.tar.gz 
   tar -xf installationFilename.tar
   ```

1. 展開したプログラムファイルを、次の表に示すディレクトリにコピーします。

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
   <td colname="col2"> コレクタロードモジュール </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> コレクタロードモジュールライブラリ </td> 
   <td colname="col3"> WebSphere /libディレクトリ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> 送信プログラム </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--OR-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書です </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsというスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールを選択することもできます）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

**プログラムファイルに対する権限**

プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。

この節に記載されているとおりに権限が設定されていることを確認してください。

デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの構成によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）場合があります。

推奨されるデフォルト設定にアクセス権をリセットするには、次のchmodコマンドを使用します。

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

推奨されるデフォルト値以外の権限を使用する場合は、「Sensor UNIX File Permissions」の情報を確認し、これらのファイルの使用方法を確認してください。

## Edit the Sensor Configuration file {#section-283c8a92fa8841c1b6034e5f834ef4e7}

txlogd.confファイルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、特に、ディスクキューのサイズ、Insightサーバーのアドレス、このセンサーによって生成されるデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* 必須パラメーターは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* オプションのパラメータは、デフォルトで事前定義済みの値（変更可能）またはオプション機能を有効にする設定です。

**設定ファイルを編集するには**

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機の開始とディスク・キューの作成 {#section-63285a2328604f20a2cb31b3d5cb80e6}

txlogd.confファイルを設定した後のディスクキューの作成手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクタ・モジュールと送信プログラムの両方に、ファイルへの読み取り/書き込みアクセス権が与えられていることを確認します。

1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機の開始を行います。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッタをインタラクティブモードで開始します。 このモードでは、送信機メッセージが画面に表示され、キーボード・コマンドを使用して送信機と対話することができます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。

1. 送信機がQueueFileパラメーターで指定された場所にディスクキューを作成し、QueueSizeパラメーターで指定されたサイズでディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の操作を行います。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作していて、QueueSizeパラメーターで指定されたサイズのファイルを保持するのに十分な領域があることを確認してください。
   1. 必要な修正を加え、この手順を繰り返します。

## Web アプリケーション追加の収集者 {#section-d17297b1193f4e3cb150fb41f754ef12}

WebSphereサーバーの場合、コレクタはサーブレットコンテナのフィルタとして機能します。

Webアプリケーションにコレクターを追加するには、Webアプリケーションのweb.xmlデプロイメント記述子にフィルターを追加し、Webアプリケーションを再起動します。

1. テキストエディターを使用して、イベントSensorが取得したWebサーバーのweb.xmlファイルを開きます。
1. 次の追加要素 `<filter>` と、記述子ファイル `<filter-mapping>` の要素。 /etcディレクトリにtxlogd.confをインストールしなかった場合は、このファイルへの正しいパスを `<param-value>` 要素に入力する必要があります。

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

1. Webアプリケーションを再起動します。 コレクタはアプリケーションと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始します。

## コレクタと共有オブジェクト・ファイルの場所の宣言 {#section-e641f08999d34a648aaee2111b69ca25}

Websphere起動スクリプトを編集して、J2EECollector.jarファイルとlibvisual_sciences.soファイルの場所を宣言する手順。

1. Websphere /binディレクトリのsetupCmdLine.shファイルを開きます。
1. $WAS_CLASSPATH変数を定義する行の後に、次の行を追加します。

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. $WAS_LIBPATH変数を定義するケースブロックの後に、次の行を追加します。

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Save the [!DNL setupCmdLine.sh] file.

## センサーのテスト {#section-07f2da5c4caa46bf9dd1cb4ae4b61af5}

送信機を開始し、Insightサーバーに接続して、イベントデータを送信できるかどうかを確認する手順です。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上で）ブラウザーを開き、Sensorが実行されているWebサーバーに対してページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信者のコンソールを調べて、送信者がイベントデータをターゲットインサイトサーバーに送信していることを示すメッセージがないかどうかを確認します。
1. センサーがデータを正常に送信しない場合は、次のことを確認します。

   * ターゲットインサイトサーバーが実行されている。
   * txtlogd.confでは、ServerAddressパラメーターとServerPortパラメーターが正しく設定されています。 サーバー名を使用してServerAddressを指定した場合は、代わりに数値のIPアドレスを使用してみてください。
   * CertNameパラメーターの値は、ターゲットインサイトサーバーのデジタル証明書に表示される共通名と完全に一致します。

## シ追加ステム起動スクリプトへの送信機 {#section-23bb905100d04f018af93873dd4d5f68}

Webサーバーコンピューターの再起動時に、送信機が自動的に読み込まれるようにする情報です。

次の追加コマンド（送信機を起動）は、システム起動スクリプトに対して実行します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして開始します。 送信機が生成する動作メッセージとエラーメッセージは、syslogに書き込まれます。

## 追加データの取得 {#section-d5ccf8ee50914a87938e0c17480757e6}

すべてのプラットフォームのセンサーは、HTTPリクエストヘッダーおよび応答ヘッダーで使用可能な任意のデータを収集できます。

J2EEプラットフォーム用のSensorは、他のプラットフォームでは利用できないデータを収集するメカニズムを提供します。 J2EEプラットフォーム（J2EEコレクタ）のコレクターは、アプリケーション層上に配置されており、この層によって、アプリケーションでのみ使用可能で、ページタグやヘッダー内に公開されない機密性の高いデータを収集できます。

>[!NOTE]
>
>ページタグやヘッダーの変更によってデータが非表示になる場合でも、ページのソースコードを調べたり、ブラウザープラグインツールを使用してヘッダーを調べたりするユーザーは、引き続き利用できます。

例えば、J2EEコレクタを使用して、ページに表示されるリンクのコストパークリック(CPC)データ、ページ上の機密性の高いパートナー情報、その他多くのデータポイントを取り込むことができます。 J2EE環境を使用すると、WEBアプリを変更して、コレクタークラスを使用してこのカスタムデータを取り込むことが簡単にできます。

J2EEプラットフォーム用のセンサーは、要求を受け取ると、appendToLog関数をインポートするコレクタークラスを呼び出します。 appendToLog関数は、最初のリクエストにappendToLog関数で指定されたクエリ文字列パラメータを追加します。 この結果、最初のリクエストのURIには、取り込まれるデータの名前と値に対応する、追加のクエリ文字列の名前と値のペアが含まれます。 例えば、特定の広告プレースメントまたはクリックスルーリンクの値が20セントの場合、CPC=20が初期リクエストに追加されます。 Insight Serverは、これらの値を分析用のデータセットに処理します。 この収集方法のもう1つの利点は、ページタギング手法を使用して作成されるように、追加のログエントリを作成することなく追加のデータを収集できる点です。

For more information about processing, see the *Dataset Configuration Guide*.

1. 次追加のコードは、データを取り込む.jspページの先頭に配置します。

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. コレクタオブジェクトのappendToLog()メソッドを使用して、必要な名前と値のペアを要求された.jspページのクエリ文字列に追加します。 次の例では、要求された.jspページの/index.jspページ用クエリ文字列に「A=1」と「B=2」を追加します。

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

   結果の要求URIは/index.jsp?A=1&amp;B=2です。

1. 追加のデータを取り込む各.jspページに対して、この手順を繰り返します。

