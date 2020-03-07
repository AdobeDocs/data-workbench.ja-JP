---
description: RedHat Linux 7.x以降、Sun Solaris SPARC 2.6以降、またはSun Solaris x86 9以降で実行するJ2EE実装用のSensorのインストールおよび設定の詳細な手順。
title: RedHat LinuxまたはSun Solaris上のJBoss、Tomcat、WebLogic Server
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RedHat LinuxまたはSun Solaris上のJBoss、Tomcat、WebLogic Server{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

RedHat Linux 7.x以降、Sun Solaris SPARC 2.6以降、またはSun Solaris x86 9以降で実行するJ2EE実装用のSensorのインストールおよび設定の詳細な手順。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

次のJ2EE実装がサポートされています。

* JBoss Server 3.2.x以降
* Apache Jakarta Tomcat Server 4.1以降
* WebLogic Server 6.x以降

Sensorをインストールして設定するには、次の手順を実行する必要があります。

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor用のプログラムファイルを抽出してインストールする手順。

1. rootユーザーまたはroot権限を持つユーザーとしてログオンします。
1. 次のコマンドを使用して、インストールファイルを解凍し、解凍します。

   * Linuxの場合：

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Solarisの場合：

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. 展開したプログラムファイルを、次の表に示すディレクトリにコピーします。

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> ターゲットディレクトリ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> コレクタロードモジュール。 </td> 
   <td colname="col3"> <i> IBMHttpServer/モジュール</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> 送信プログラム。 </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>--OR--</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル。 </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書 </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールは可能です）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

**プログラムファイルの権限**

>[!NOTE]
>
>プログラムファイルに対する権限が正しくないと、Sensorのインストール時に発生する問題の大部分が発生します。 この節で説明したとおりに権限が設定されていることを確認してください。
>
>デフォルトでは、tarファイル内のプログラムファイルには次の権限があります。 システムの設定によっては、ファイルを抽出する際に、これらの設定が変更（マスクされない）される場合があります。 推奨されるデフォルト設定に権限をリセットするには、次のchmodコマンドを使用します。 ファイルをインストールしたディレクトリで、少なくともこのレベルのアクセスが許可されていることを確認します。

| File | デフォルトの権限 | chmodコマンド |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw-r— r— | chmod 664 |
| trust_ca_cert.pem | rw-r— r— | chmod 664 |

## センサー設定ファイルの編集 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

このファ [!DNL txlogd.conf] イルには、Sensorの設定パラメーターが含まれています。

このファイルを編集して、特に、ディスクキューファイルのサイズと場所、Insightサーバーのアドレス、およびこのセンサーによって生成されるイベントデータに添付されるIDを指定する必要があります。

設定ファイルには、必須パラメーターとオプションのパラメーターが含まれています。

* **必須パラメータ** ーは、Sensorのインストール時に指定する必要がある設定です。 これらの設定がないと、Sensorは正常に実行されません。
* **オプションのパラメータ** は、デフォルトで事前定義された値（変更可能）に設定される設定、またはオプション機能を有効にする設定です。

**Sensor設定ファイルを編集するには**

* テキストエデ [!DNL /etc/txlogd.conf] ィターでファイルを開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
* ファイルを保存して閉じます。

**Sensor設定ファイルを編集するには**

1. テキストエデ [!DNL /etc/txlogd.conf] ィターでファイルを開き、必要なパラメーターと必要なオプションのパラメーターを設定します。
1. ファイルを保存して閉じます。

## 送信機を起動し、ディスク・キューを作成する {#section-55630de65f264274aefd771da2002852}

txlogd.confファイルを設定したら、送信プログラムを起動し、Windowsサービスとして登録し、ディスクキューを作成します。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリがコレクタ・モジュールと送信プログラムの両方にファイルへの読み取り/書き込みアクセスを提供していることを確認します。

   ディスクキューファイルに必要な権限について詳しくは、Sensor UNIX File Permissionsを参照してください。
1. Sensorがインストールされているコンピューターで、次のコマンドを実行して送信機を起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、送信機を「インタラクティブ・モード」で起動します。このモードは、送信機のメッセージを画面に表示し、キーボードコマンドを使用して送信機とやり取りすることもできます。
   * 「c」オプションは、送信機にディスク・キューを作成するよう指示します。
   * 「f」オプションは設定ファイルの場所を指定します。
   送信機の起動時に使用できるオプションについて詳しくは、Sensor Transmitter Command-Line Optionsを参照してください。

1. 送信機が、QueueFileパラメーターで指定された場所と、QueueSizeパラメーターで指定されたサイズのディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl + Cキーを押して送信機を終了し、次の手順を実行します。

   1. txtlogd.confファイルを調べ、QueueFileパラメーターとQueueSizeパラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSizeパラメータで指定されたサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Webサーバーへのコレクタの追加 {#section-c5b83ae4ebce430aa764f951e849b333}

Apacheサーバーの場合、コレクターは、Webサーバープロセスに読み込む動的共有オブジェクトです。

Webサーバーにコレクターを追加するには、以下の説明に従ってファ [!DNL httpd.conf] イルを編集し、Webサーバーを再起動する必要があります。

>[!NOTE]
>
>Sensorがサーバーコンピューター上の複数のWebサーバーのデータを取り込む場合は、各Webサーバーに対して次の手順を実行する必要があります。

1. テキストエディターを使用して、Sensorで取 [!DNL httpd.conf]り込んだイベントを含むWebサーバーのファイルを開きます。
1. 次の要素と要素を `<filter>` 記述子 `<filter-mapping>` ファイルに追加します。 /etcディレクトリにtxlogd.confをインストールしなかった場合は、次の要素にこのファイルの正しいパスを入力する必要があり `<param-value>` ます。

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
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

1. Webサーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はなく、Webサーバープロセスを再起動します）。 コレクタは、Webサーバと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始する。

## センサーのテスト {#section-0dae181ef8884f10a57f6cfda8500969}

コレクターがイベントデータを収集し、送信者がそのデータをターゲットのInsightサーバーに送信していることを確認します。

>[!NOTE]
>
>送信機がイベントデータをInsightサーバーに正常に送信できることを確認するには、次のテストを開始する前に、ターゲットのInsightサーバーがインストールされ、実行されていることを確認します。

1. トランスミッタがまだ実行されていない場合は、次のコマンドを使用して再起動します。

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. （任意のマシン上の）ブラウザーを開き、Sensorが実行されているWebサーバーからページを要求します（Sensorが監視しているページを必ず選択してください）。
1. リクエストを発行した後、送信機のコンソールで、送信機がターゲットのInsightサーバーにイベントデータを送信していることを示すメッセージを確認します。
1. センサーがデータを正常に送信しない場合は、次の点を確認します。

   * 対象のInsightサーバーが実行中です。
   * txtlogd.confでServerAddressパラメーターとServerPortパラメーターが正しく設定されている。 サーバー名を使用してServerAddressを指定した場合は、代わりに数値のIPアドレスを使用してみてください。
   * CertNameパラメーターの値は、ターゲットInsightサーバーのデジタル証明書に表示される共通名と完全に一致します。

## システム起動スクリプトへの送信機の追加 {#section-19a38f27c9f44adf88f8910f5ed483a3}

システムの起動スクリプトへの送信機の自動読み込みに関する情報です。

Webサーバー・マシンの再起動時に送信機が自動的に読み込まれるようにするには、次のコマンド（送信機を起動するコマンド）をシステムの起動スクリプトに追加します。

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

このコマンドは、送信機をデーモンとして起動します。 送信機が生成する操作メッセージとエラーメッセージが書き込まれま [!DNL syslog]す。

デフォルトのSolaris設定は60です。 各インスタンスに3つのセマフォーを使用するSensorで実行されたテストに基づいて、1024を設定として使用することをお勧めします。 この数値は、セマフォーを必要とする可能性のある他のアプリケーションと共にSensorが機能するのに十分な値ですが、パフォーマンスには影響しません。 この推奨を支持するため、Adrian Cockcroftは著書Sun Performance and Tuning（Prentice Hall、1994年10月）で以下の内容を述べています。「データベースは、多くの共有メモリとセマフォの設定を使う傾向があります。 これらはパフォーマンスに影響を与えません。十分大きい限り、プログラムは動く」

## 追加データの取得 {#section-9483b663cbd0432daaca50c1089c7fca}

すべてのプラットフォームのセンサーは、HTTPリクエストおよび応答ヘッダーで使用可能な任意のデータを収集できます。

J2EEプラットフォーム用のSensorは、他のプラットフォームでは利用できないデータを収集するメカニズムを提供します。 J2EEプラットフォーム（J2EEコレクタ）のコレクタは、アプリケーションレイヤー上に配置され、アプリケーションでのみ使用可能で、ページタグやヘッダーで公開しない機密データを収集できます。

>[!NOTE]
>
>ページタグやヘッダの変更によってデータが非表示になる場合でも、ページのソースコードを調べたり、ブラウザプラグインツールを使用してヘッダを確認したりするユーザは、引き続き使用できます。

例えば、J2EEコレクタを使用して、ページに表示されるリンクのコストパークリック(CPC)データ、ページ上の機密パートナー情報、その他多くのデータポイントを取得できます。 J2EE環境を使用すると、WEBAPPを変更して、コレクタークラスを使用してこのカスタムデータを取り込むことが簡単にできます。

J2EEプラットフォーム用のSensorは、リクエストを受け取ると、appendToLog関数をインポートするコレクタークラスを呼び出します。 appendToLog関数は、最初のリクエストにappendToLog関数で指定されたクエリ文字列パラメータを追加します。 この結果、取り込まれるデータの名前と値に対応する追加のクエリ文字列の名前と値のペアが含まれる最初のリクエストのURIが生成されます。 例えば、特定の広告配置またはクリックスルーリンクの値が20セントの場合、CPC=20が最初のリクエストに追加されます。 Insight Serverは、分析のためにこれらの値をデータセットに処理します。 この収集方法のもう1つの利点は、ページタギング手法を使用して作成されるように、追加のログエントリを作成せずに追加のデータを収集できることです。

処理について詳しくは、『データセット設定ガイド』を参照してください。

**ページから追加のデータを取り込むには**

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

