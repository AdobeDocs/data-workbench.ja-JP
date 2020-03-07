---
description: Apache Server 1.3、Apache Server 2.0.42以降、またはMicrosoft Windows Server 2000以降で実行されるApache Server 2.2用のSensorのインストールおよび設定の手順。
title: Windows Server 2000以降で稼働するApache Server 1.3、2、2.2または2.4
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Windows Server 2000以降で稼働するApache Server 1.3、2、2.2または2.4{#apache-server-or-on-windows-server-or-later}

Apache Server 1.3、Apache Server 2.0.42以降、またはMicrosoft Windows Server 2000以降で実行されるApache Server 2.2用のSensorのインストールおよび設定の手順。

Sensorのプログラムファイルは、アドビのダウンロードサイトから入手したインストールファイルにパッケージ化されています。 お使いのWebサーバー用のSensorインストールファイルがまだない場合は、次の手順を開始する前に、ダウンロード（またはアドビの担当者から入手）してください。

* Apache Server 1.3
* Apache Server 2.0.42以降
* Microsoft Windows Server 2000以降で稼働するApache Server 2.2

## Install the Program Files {#section-2f3e85083b4f4aa989a85997330e86ae}

プログラムファイルをインストールする前に、ディスクキューを保持する場所も指定する必要があります。これは、プログラムファイルをインストールする必要があるためです。 Sensor用のプログラムファイルの抽出とインストールの手順です。

Sensorをインストールして設定するには、次の手順を実行する必要があります。

1. Windowsコンピューターで、Sensorプログラムファイルをインストールするディレクトリを作成します。 ディスクキューもこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な領域があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. 作成したディレクトリにインストールファイルの内容を抽出します。 この手順で、Sensorは次のファイルをインストールします。

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ファイル </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> イベントビューアのメッセージ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> コレクタモジュール。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestTest.xls </p> </td> 
   <td colname="col2"> <p>設計者が制御実験の設定に使用できるExcelスプレッドシートファイル。 センサーはこのファイルを使用しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中にInsightサーバーが提示するデジタル証明書の検証に使用される証明書です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 送信プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor設定ファイル </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestTest.xlsという名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、設計者が制御実験を設定する際に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensorを実行しているコンピューターにファイルをインストールする必要はありません（ただし、インストールは可能です）。 必要に応じて、設計者がアクセスできる場所にファイルをコピーするか、インストールパッケージからファイルを抽出します。 対照実験について詳しくは、『Insight Controlled Experiments Guide』を参照してください。

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
1. ファイルの末尾に次の2行を追加します。

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Webサーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はなく、Webサーバープロセスを再起動します）。 コレクタは、Webサーバと共に読み込まれ、イベントデータの収集とディスクキューへの書き込みを開始する。

