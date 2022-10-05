---
description: Sensor for Apache Server 1.3、Apache Server 2.0.42 以降、またはMicrosoft Windows Server 2000 以降で実行されている Apache Server 2.2 用の Sensor のインストールと設定の手順。
title: Apache サーバー 1.3、2、2.2、2.4（Windows Server 2000 以降）
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 2%

---

# Apache サーバー 1.3、2、2.2、2.4（Windows Server 2000 以降）{#apache-server-or-on-windows-server-or-later}

{{eol}}

Sensor for Apache Server 1.3、Apache Server 2.0.42 以降、またはMicrosoft Windows Server 2000 以降で実行されている Apache Server 2.2 用の Sensor のインストールと設定の手順。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

* Apache サーバー 1.3
* Apache Server 2.0.42 以降
* Microsoft Windows Server 2000 以降で動作する Apache Server 2.2

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

プログラムファイルをインストールする前に、ディスクキューを保持する場所を決定する必要があります。その場所は、プログラムファイルをインストールする必要もあります。

Sensor をインストールして設定するには、次の手順を実行する必要があります。

1. Windows マシン上に、Sensor プログラムファイルをインストールするディレクトリを作成します。 ディスクキューもこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な空き容量があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. 作成したディレクトリに、インストールファイルの内容を抽出します。 この手順の間、Sensor は以下のファイルをインストールします。

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
   <td colname="col2"> イベントビューアメッセージ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> コレクターモジュール。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>アーキテクトが対照実験の設定に使用できる Excel スプレッドシートファイル。 センサーはこのファイルを使用しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中に Insight サーバーが提示する電子証明書を検証するために使用される証明書です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 送信機プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Sensor 設定ファイル </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestExperiment.xls という名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールすることは可能です）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

## センサー設定ファイルの編集 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

この [!DNL txlogd.conf] ファイルには、Sensor の設定パラメータが含まれています。

このファイルを編集して、ディスクキューファイルのサイズと場所、Insight サーバーのアドレス、このセンサーによって生成されるイベントデータに添付される ID を指定する必要があります。

設定ファイルには、必須のパラメーターとオプションのパラメーターが含まれています。

* **必須パラメーター** は、Sensor をインストールする際に指定する必要がある設定です。 これらの設定がないと、センサーは正常に動作しません。
* **オプションのパラメーター** は、事前定義済みの値（変更可能）をデフォルトにする設定またはオプション機能を有効にする設定です。

**Sensor 設定ファイルを編集するには**

* を開きます。 [!DNL /etc/txlogd.conf] ファイルを編集し、必要なパラメーターと必要なオプションパラメーターを設定します。
* ファイルを保存して閉じます。

**Sensor 設定ファイルを編集するには**

1. を開きます。 [!DNL /etc/txlogd.conf] ファイルを編集し、必要なパラメーターと必要なオプションパラメーターを設定します。
1. ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-55630de65f264274aefd771da2002852}

txlogd.conf ファイルを設定した後、トランスミッタープログラムを起動し、Windows サービスとして登録し、ディスクキューを作成できます。

1. ディスクキューが存在するディレクトリが存在しない場合は、作成します。 ディレクトリに、コレクターモジュールとトランスミッタープログラムの両方に、ファイルへの読み取り/書き込みアクセス権が付与されていることを確認します。

   ディスクキューファイルに必要な権限の詳細については、「 Sensor UNIX File Permissions 」を参照してください。
1. センサーがインストールされているコンピューターで、次のコマンドを実行してトランスミッターを起動します。

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * このコマンドの「i」オプションは、トランスミッターを「インタラクティブモード」で開始します。 このモードでは、トランスミッターメッセージを画面に表示し、キーボードコマンドを使用してトランスミッターを操作できます。
   * 「c」オプションは、トランスミッターにディスクキューを作成するよう指示します。
   * 「f」オプションは、設定ファイルの場所を指定します。

   トランスミッターの開始時に使用できるオプションの詳細については、センサートランスミッターのコマンドラインオプションを参照してください。

1. トランスミッターが、QueueFile パラメーターで指定された場所と、QueueSize パラメーターで指定されたサイズにディスクキューを作成したことを確認します。
1. キューが正しく作成されていない場合は、Ctrl+C キーを押してトランスミッターを終了し、次の手順を実行します。

   1. txtlogd.conf ファイルを調べ、QueueFile および QueueSize パラメーターが正しく設定されていることを確認します。
   1. ディスクキューが割り当てられているデバイスが動作し、QueueSize パラメータで指定されたサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. 必要な修正を加え、この手順を繰り返します。

## Web サーバーにコレクタを追加する {#section-c5b83ae4ebce430aa764f951e849b333}

Apache サーバーの場合、コレクターは、Web サーバープロセスに読み込む動的共有オブジェクトです。

Web サーバーにコレクターを追加するには、 [!DNL httpd.conf] ファイルを開き、web サーバーを再起動します。

>[!NOTE]
>
>センサーがサーバーコンピューター上の複数の Web サーバーのデータをキャプチャする場合は、各 Web サーバーで次の手順を実行する必要があります。

1. テキストエディターを使用して、 [!DNL httpd.conf]ファイルを作成します。
1. ファイルの末尾に次の 2 行を追加します。

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >これらの行では大文字と小文字が区別されます。 上に表示されたとおりに入力します。

1. Web サーバープロセスを再起動します（サーバーコンピューター全体を再起動する必要はありません。Web サーバープロセスを再起動するだけです）。 コレクタは Web サーバと共にロードされ、イベントデータの収集とディスクキューへの書き込みを開始します。
