---
description: Microsoft Windows Server 2000 以降で実行されている Windows 3.1 以降用の Lotus Domino Server 6 のインストールおよび構成方法に関する手順。
title: Lotus Domino サーバー（Windows Server 2000 以降）
uuid: e3fb1478-92d1-4488-a4b8-244d258cc00a
exl-id: b736c8e6-0642-419c-8715-6586c21f2182
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 2%

---

# Lotus Domino サーバー（Windows Server 2000 以降）{#lotus-domino-server-on-windows-server-or-later}

{{eol}}

Microsoft Windows Server 2000 以降で実行されている Windows 3.1 以降用の Lotus Domino Server 6 のインストールおよび構成方法に関する手順。

Sensor のプログラムファイルは、インストールファイルにパッケージ化され、Adobeダウンロードサイトから入手できます。 ご使用の Web サーバー用の Sensor インストールファイルがまだない場合は、次の手順を開始する前に、そのファイルをダウンロード ( またはAdobe担当者から入手 ) してください。

Sensor をインストールして設定するには、次の手順を実行する必要があります。

## プログラムファイルのインストール {#section-2f3e85083b4f4aa989a85997330e86ae}

1. Lotus Domino マシン上に、Sensor プログラムファイルをインストールするディレクトリを作成します。 ディスクキューもこのディレクトリに存在するので、選択したデバイスに必要なサイズのキューを保持するのに十分な空き容量があることを確認してください。

   ```
   C:\VisualSensor
   ```

1. インストールファイルの内容を Lotus Domino ディレクトリに抽出します。 この手順の間、Sensor は以下のファイルをインストールします。

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
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> コレクターモジュール </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>アーキテクトが対照実験の設定に使用できる Excel スプレッドシートファイル </p> <p>センサーはこのファイルを使用しません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> 接続プロセス中に Insight サーバーが提示する電子証明書を検証するために使用される証明書 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> 送信機プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> Sensor 設定ファイル </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>インストールパッケージには、TestExperiment.xls という名前のスプレッドシートファイルが含まれています。 このスプレッドシートは、アーキテクトが対照実験の設定に使用するツールです。 センサー自体はこのファイルを使用しないので、Sensor が実行されているマシンにファイルをインストールする必要はありません（ただし、インストールすることは可能です）。 代わりに、アーキテクトがアクセスできる場所にファイルをコピーするか、必要に応じてインストールパッケージからファイルを抽出します。 対照実験の詳細については、『 Insight 対照実験ガイド』を参照してください。

## Lotus Domino サーバーの構成 {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Lotus Domino サーバーを構成する手順です。

1. Lotus Domino 管理者にログインし、 **[!UICONTROL Domain]**.

   ![](assets/dom_svr1.png)

1. Lotus Domino 管理者で、 **[!UICONTROL Configuration]**.

   ![](assets/dom_svr2.png)

1. 「サーバー」ノードを展開し、 **[!UICONTROL Current Server Document]**.

   ![](assets/dom_svr3.png)

1. 「**[!UICONTROL Current Server Document]**」、「**[!UICONTROL Internet Protocols]**」の順にクリックします。

   ![](assets/dom_svr4.png)

1. 「HTTP」タブの「DSAPI」セクションで、「 [!DNL ndolextn].

   ![](assets/dom_svr5.png)

1. 押す **[!UICONTROL Enter]** をクリックし、 [!DNL dominosensor.dll] ファイル。

   ![](assets/dom_svr6.png)

1. 「**[!UICONTROL Save & Close]**」をクリックします。

   ![](assets/dom_svr7.png)

## センサー設定ファイルの編集 {#section-de0eb4a646394b61abb6cd5a2b706de0}

txlogd.conf ファイルには、Sensor の設定パラメーターが含まれています。

このファイルを編集して、ディスクキューファイルのサイズと場所、Insight サーバーのアドレス、このセンサーによって生成されるイベントデータに添付される ID を指定する必要があります。

設定ファイルには、必須のパラメーターとオプションのパラメーターが含まれています。

* **必須パラメーター** は、Sensor をインストールする際に指定する必要がある設定です。 これらの設定がないと、センサーは正常に動作しません。
* **オプションのパラメーター** は、事前定義済みの値（変更可能）をデフォルトにする設定またはオプション機能を有効にする設定です。

**Sensor 設定ファイルを編集するには**

* を開きます。 `<Sensor directory>/txlogd.conf` ファイルを編集し、必要なパラメーターと必要なオプションパラメーターを設定します。
* ファイルを保存して閉じます。

## トランスミッターを起動し、ディスクキューを作成します。 {#section-55630de65f264274aefd771da2002852}

txlogd.conf ファイルを設定した後、トランスミッタープログラムを起動し、Windows サービスとして登録し、ディスクキューを作成できます。

1. Windows の [ スタート ] メニューから、 **アクセサリ** > **コマンドプロンプト**.

1. コマンドプロンプトウィンドウで、Sensor をインストールしたディレクトリに移動し、次のコマンドを実行します。

   ```
   txlog /regserver
   ```

   このコマンドは、トランスミッターを起動し、ディスクキューを作成し、Sensor を Windows サービスとして登録します。

1. トランスミッターが正しく動作していることを確認するには、 **スタート/Campaign コントロールパネル/管理ツール/サービス**.

   >[!NOTE]
   >
   >このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. サービスリストで、Sensor のエントリを探し、そのステータスが「開始済み」で、起動タイプが「自動」であることを確認します。
   1. [ サービス ] コントロールパネルを閉じます。

1. 起動中にトランスミッターでエラーが発生したかどうかを確認するには、スタート/Campaign コントロールパネル/管理ツール/イベントビューアをクリックして、イベントビューアを開きます。

   >[!NOTE]
   >
   >このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. [Event Viewer] ウィンドウの左ペインで、[Applications] ログを選択します。
   1. 右側のウィンドウで、「ソース」列に「Adobe」があるイベントを探します。
   1. 「Adobe」からエラーが見つかった場合は、そのエラーをダブルクリックして「イベントのプロパティ」ウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

1. アプリケーションログの調査が終了したら、イベントビューアを閉じます。
1. トランスミッターがディスクキューを作成した ( [!DNL Diskq2000.log]) は、Sensor プログラムファイルをインストールしたディレクトリにあり、それが [!DNL QueueSize] パラメーター [!DNL txlogd.conf] ファイル。

   キューが正しく作成されていない場合：

   1. txtlogd.conf ファイルを調べ、QueueSize パラメーターが正しく設定されていることを確認します。
   1. Sensor をインストールしたデバイスに、QueueSize パラメータで指定したサイズのファイルを保持するのに十分な空き容量があることを確認します。
   1. Windows のサービスコントロールパネルで、トランスミッターを停止します。
   1. キューファイルを削除します。
   1. センサーを Windows サービスとして再登録：Windows の [ スタート ] メニューから、[ アクセサリ ] > [ コマンドプロンプト ] を選択します。 コマンドプロンプトウィンドウで、Sensor をインストールしたディレクトリに移動し、次のコマンドを実行します。

      ```
      txlog /regserver
      ```

      トランスミッターは、連続的に実行するように設計されています。 コンピューターを再起動すると、トランスミッターが自動的に再起動します。 トランスミッターを手動で起動および停止する必要がある場合は、Windows の [ サービス ] コントロールパネルを使用して実行できます。
