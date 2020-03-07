---
description: AIX 5.1以降で実行するWebSphere 5.x用のSensorのインストールおよび設定に関する詳細な手順です。
solution: Insight
title: WebSphere(AIX)
uuid: a5a3fd79-a7f0-4861-adca-8da3a185d0df
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WebSphere(AIX){#websphere-on-aix}

AIX 5.1以降で実行するWebSphere 5.x用のSensorのインストールおよび設定に関する詳細な手順です。

のプログラムファイルは、ア [!DNL Sensor] ドビのダウンロードサイトから入手したインストールファイルにパッケージ化されています。 ご使用のWebサーバーのインストールファ [!DNL Sensor] イルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

>[!NOTE]
>
>WebSphereサーバ [!DNL Sensor] ー用は、制御実験をサポートしていません。 実験の制御について詳しくは、『 *Data Workbench Controlled Experiments Guide』を参照してください。*

## Install the Program Files {#section-86f69127278c41bc90b97b68bb40bc6e}

Sensorのプログラムファイルを抽出し、サーバーマシンにインストールする手順。

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
   <td colname="col2"> コレクタのロードモジュールライブラリ </td> 
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
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書 </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールする必要はありません）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

**プログラムファイルの権限**

プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。

この節で説明したとおりに権限が設定されていることを確認してください。

デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）される場合があります。

推奨されるデフォルト設定に権限をリセットするには、次のchmodコマンドを使用します。

>[!NOTE]
>
>ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| File | デフォルトの権限 | chmodコマンド |
|---|---|---|
| libvisual_sciences.so | rwx —x —x | chmod 711 |
| J2EECollector.jar | rw-rw- r— | chmod 664 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-rw- r— | chmod 664 |
| trust_ca_cert.pem | rw-rw- r— | chmod 664 |

推奨されるデフォルト以外の権限を使用する場合は、「Sensor UNIX File Permissions」の情報を確認し、これらのファイルの使用方法を確認します。

## Sensor設定ファイルの編集 {#section-283c8a92fa8841c1b6034e5f834ef4e7}

txlogd.confファイルには、Sensorの設定パラメーターが含まれています。

ファイルを編集して、特に、ディスクキューのサイズ、Insightサーバーのアドレス、およびこのセンサーで生成されるデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* 必須パラメーターは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* オプションのパラメーターは、デフォルトで事前定義済みの値（変更可能）に設定される設定、またはオプション機能を有効にする設定です。

**設定ファイルを編集するには**

1. /etc/txlogd.confファイルをテキストエディターで開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機を起動し、ディスク・キューを作成する {#section-63285a2328604f20a2cb31b3d5cb80e6}

txlogd.confファイルを設定した後の、ディスクキューの作成手順。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリがコレクタ・モジュールと送信プログラムの両方にファイルへの読み取り/書き込みアクセスを提供していることを確認します。

1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機を起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、送信機をインタラクティブ・モードで起動します。 このモードは、送信機のメッセージを画面に表示し、キーボードコマンドを使用して送信機とやり取りすることもできます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。

1. 送信機が、QueueFileパラメーターで指定された場所と、QueueSizeパラメーターで指定されたサイズのディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の手順を実行します。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSizeパラメータで指定されたサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Webアプリケーションへのコレクタの追加 {#section-d17297b1193f4e3cb150fb41f754ef12}

WebSphereサーバーの場合、コレクターはサーブレットコンテナ内のフィルターとして機能します。

Webアプリケーションにコレクターを追加するには、Webアプリケーションのweb.xmlデプロイメント記述子にフィルターを追加し、Webアプリケーションを再起動します。

1. テキストエディターを使用して、Sensorが取り込むイベントのWebサーバーのweb.xmlファイルを開きます。
1. 次の要素と要素を `<filter>` 記述子 `<filter-mapping>` ファイルに追加します。 /etcディレクトリにtxlogd.confをインストールしなかった場合は、このファイルへの正しいパスを要素に入力する必要があり `<param-value>` ます。

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

## コレクターと共有オブジェクトファイルの場所の宣言 {#section-e641f08999d34a648aaee2111b69ca25}

Websphere起動スクリプトを編集して、J2EECollector.jarおよびlibvisual_sciences.soファイルの場所を宣言する手順。

1. Websphereの/binディレクトリにあるsetupCmdLine.shファイルを開きます。
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

送信機を起動し、Insightサーバーに接続して、イベントデータを送信できることを確認する手順です。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットのInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上の）ブラウザーを開き、Sensorが実行されているWebサーバーからページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信機のコンソールで、送信機がターゲットのInsightサーバーにイベントデータを送信していることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次のことを確認します。

   * 対象のInsightサーバーが実行中です。
   * txtlogd.confでServerAddressパラメーターとServerPortパラメーターが正しく設定されている。 サーバー名を使用してServerAddressを指定した場合は、代わりに数値のIPアドレスを使用してみてください。
   * CertNameパラメーターの値は、ターゲットInsightサーバーのデジタル証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへの送信機の追加 {#section-23bb905100d04f018af93873dd4d5f68}

Webサーバーコンピューターの再起動時に送信機が自動的に読み込まれるようにする情報です。

次のコマンド（送信機を起動するコマンド）をシステム起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして起動します。 送信機が生成する動作メッセージとエラーメッセージはsyslogに書き込まれます。

## 追加データの取得 {#section-d5ccf8ee50914a87938e0c17480757e6}

すべてのプラットフォームのセンサーは、HTTPリクエストおよび応答ヘッダーで使用可能な任意のデータを収集できます。

J2EEプラットフォーム用のSensorは、他のプラットフォームでは利用できないデータを収集するメカニズムを提供します。 J2EEプラットフォーム（J2EEコレクタ）のコレクタは、アプリケーションレイヤー上に配置され、アプリケーションでのみ使用可能で、ページタグやヘッダーで公開しない機密データを収集できます。

>[!NOTE]
>
>ページタグやヘッダの変更によってデータが非表示になる場合でも、ページのソースコードを調べたり、ブラウザプラグインツールを使用してヘッダを確認したりするユーザは、引き続き使用できます。

例えば、J2EEコレクタを使用して、ページに表示されるリンクのコストパークリック(CPC)データ、ページ上の機密パートナー情報、その他多くのデータポイントを取得できます。 J2EE環境を使用すると、WEBAPPを変更して、コレクタークラスを使用してこのカスタムデータを取り込むことが簡単にできます。

J2EEプラットフォーム用のSensorは、リクエストを受け取ると、appendToLog関数をインポートするコレクタークラスを呼び出します。 appendToLog関数は、最初のリクエストにappendToLog関数で指定されたクエリ文字列パラメータを追加します。 この結果、取り込まれるデータの名前と値に対応する追加のクエリ文字列の名前と値のペアが含まれる最初のリクエストのURIが生成されます。 例えば、特定の広告配置またはクリックスルーリンクの値が20セントの場合、CPC=20が最初のリクエストに追加されます。 Insight Serverは、分析のためにこれらの値をデータセットに処理します。 この収集方法のもう1つの利点は、ページタギング手法を使用して作成されるように、追加のログエントリを作成せずに追加のデータを収集できることです。

For more information about processing, see the *Dataset Configuration Guide*.

1. データを取り込む.jspページの先頭に次のコードを追加します。

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. コレクタオブジェクトのappendToLog()メソッドを使用して、要求された.jspページのクエリ文字列に目的の名前と値のペアを追加します。 次の例では、/index.jspページの要求された.jspページのクエリ文字列に「A=1」と「B=2」を追加します。

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

1. 追加のデータを取り込む.jspページごとに、この手順を繰り返します。

