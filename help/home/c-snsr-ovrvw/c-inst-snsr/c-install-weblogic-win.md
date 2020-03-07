---
description: Microsoft Windows Server 2000以降で実行するWebLogic Server 6.x以降用のSensorのインストールおよび設定の詳細な手順です。
title: WebLogic Server（Windows Server 2000以降）
uuid: 80dbf544-bd09-4af8-bb05-4032eb49dd5d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WebLogic Server（Windows Server 2000以降）{#weblogic-server-on-windows-server-or-later}

Microsoft Windows Server 2000以降で実行するWebLogic Server 6.x以降用のSensorのインストールおよび設定の詳細な手順です。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されます。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

Sensorをインストールして設定するには、次の手順を実行する必要があります。

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

Sensor用のプログラムファイルを抽出してインストールする手順。

1. WebLogic Serverで、Sensorプログラムファイルをインストールするディレクトリを作成します。 ディスクキューはこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な領域があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. 作成したディレクトリにインストールファイルの内容を抽出します。 この手順で、Sensorは次のファイルをインストールします。

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
   <td colname="col1"> visual_sciences.dll </td> 
   <td colname="col2"> コレクタロードモジュール。 </td> 
   <td colname="col3"> 任意のディレクトリ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> コレクタのロードモジュールライブラリ </td> 
   <td colname="col3"> WEB-INF/lib </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.exe </p> </td> 
   <td colname="col2"> 送信プログラム。 </td> 
   <td colname="col3"> 任意のディレクトリ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル。 </td> 
   <td colname="col3"> 任意のディレクトリ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書 </td> 
   <td colname="col3"> 任意のディレクトリ </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、という名前のスプレッドシートファイルが含まれてい [!DNL TestExperiment.xls]ます。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールは可能です）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

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

1. Windowsのスタートメニューで、アクセサリ/コマンドプロンプトを選択します。
1. コマンドプロンプトウィンドウで、Sensorをインストールしたディレクトリに移動し、次のコマンドを実行します。

   ```
   txlog /regserver
   ```

   このコマンドは、トランスミッタを起動し、ディスクキューを作成し、SensorをWindowsサービスとして登録します。

1. 送信機が正しく動作していることを確認するには、スタート/コントロールパネル/管理ツール/サービスをクリックします。

   >[!NOTE]
   >
   >このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。

   1. サービスリストで、Sensorのエントリを探し、ステータスがStartedで、スタートアップの種類がAutomaticであることを確認します。
   1. [サービス]コントロールパネルを閉じます。

1. 起動中に送信機でエラーが発生したかどうかを確認するには、スタート/コントロールパネル/管理ツール/イベントビューアをクリックし、イベントビューアを開きます。

   1. 「Event Viewer」ウィンドウの左ペインで、「Applications」ログを選択します。
   1. 右側のウィンドウで、「Source」列に「Adobe」が含まれているイベントを探します。
   1. 「アドビ」からエラーが見つかった場合は、エラーをダブルクリックして、イベントのプロパティウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. アプリケーションログの確認が完了したら、イベントビューアを閉じます。
1. 送信機が、Sensorプログラムファイルをインストールしたディレクトリにディスクキュー(Diskq2000.log)を作成し、txlogd.confファイルのQueueSizeパラメーターで指定したサイズであることを確認します。

   キューが正しく作成されていない場合：

   1. txtlogd.confファイルを調べ、QueueSizeパラメーターが正しく設定されていることを確認します。
   1. Sensorをインストールしたデバイスに、QueueSizeパラメーターで指定したサイズのファイルを保持するのに十分な空き領域があることを確認します。
   1. Windowsのサービス・コントロール・パネルを使用して、送信機を停止します。
   1. キューファイルを削除します。
   1. SensorをWindowsサービスとして再登録します。windowsのスタートメニューから、アクセサリ/コマンドプロンプトを選択します。 コマンドプロンプトウィンドウで、Sensorをインストールしたディレクトリに移動し、次のコマンドを実行します。

      ```
      txlog /regserver
      ```

送信機は、連続的に動作するように設計されています。 コンピューターを再起動すると、送信機が自動的に再起動します。 送信機を手動で起動および停止する必要がある場合は、Windowsのサービスコントロールパネルを使用して実行できます。

## Webサーバーへのコレクタの追加 {#section-c5b83ae4ebce430aa764f951e849b333}

JBossサーバーの場合、コレクターはサーブレットコンテナ内のフィルターとして機能します。

Webサーバーにコレクターを追加するには、以下の説明に従ってファイルを編集し、Web [!DNL web.xml] アプリケーションを再起動する必要があります。

1. テキストエディターを使用して、Sensorで取 [!DNL web.xml] り込んだイベントを持つWebサーバーのファイルを開きます。
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

1. Webサーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はなく、Webサーバープロセスを再起動します）。 コレクタは、Webサーバと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始する。

## 起動スクリプトの変更 {#section-0dae181ef8884f10a57f6cfda8500969}

起動スクリプトの変更手順。

WebLogicの起動に使用するスクリプト(例：C:\bea\user_projects\mydomain\startServer.cmd)で、「set JAVA_OPTIONS=」行を編集し、java.library.pathの定義をvisual_sciences.dllファイルを含むディレクトリに設定します。

```
set JAVA_OPTIONS=-Djava.library.path=C:\Sensor 
    directory
```

## 追加データの取得 {#section-9483b663cbd0432daaca50c1089c7fca}

appendToLog()機能を使用して、J2EEベースのWebアプリケーションから追加の測定データを取り込むことができます。

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

