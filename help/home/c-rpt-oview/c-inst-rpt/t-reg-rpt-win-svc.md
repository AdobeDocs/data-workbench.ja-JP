---
description: Report Serverを登録して実行する手順です。
solution: Analytics
title: WindowsサービスとしてのReport Serverの登録
topic: Data workbench
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# WindowsサービスとしてのReport Serverの登録{#registering-report-server-as-a-windows-service}

Report Serverを登録して実行する手順です。

この手順を実行する前に、サービスを実行するWindowsアカウントを [!DNL Report Server] 指定します。 このアカウントに、生成されたレポートが保存される場所（つまり、を使用しないでください）にアクセスする適切な権限があることを確認してくだ [!DNL Local System Account]さい。

開始するには、次の手順に従いま [!DNL Report Server]す。 初めて起動す [!DNL Report Server] ると、自動的にWindowsサービスとして登録されます。

[!DNL Report Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

1. Windowsで、をインストールしたディレクトリに移動しま [!DNL Report Server]す。

   例：D:\Adobe\Report

1. ダブルクリック **[!UICONTROL ReportServer.exe]**.
1. が正しく実行され [!DNL Report Server] ていることを確認するには、/// **[!UICONTROL Start]** をク **[!UICONTROL Control Panel]** リック **[!UICONTROL Administrative Tools]** しま **[!UICONTROL Services]**&#x200B;す。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。
1. サービスリストで、のエントリを見つけ、そのエ [!DNL Report Server] ントリのステータスが「開始」で、スタートアップの種類が「自動」であることを確認します。
1. 実行するユーザーアカウントを指定するには、次の手順 [!DNL Report Server] を実行します。

   1. ダブルクリックし **[!UICONTROL Report Server]** てウィンドウを開 [!DNL Properties] きます。

   1. タブを選択 **[!UICONTROL Log On]** します。
   1. ラジオボタン **[!UICONTROL This account]** を選択します。
   1. アカウント名を入力または参照します。 このアカウントには、生成されたレポートが保存される場所にアクセスする権限が必要です。

      >[!NOTE]
      >
      >レポート [!DNL Report Server] をMicrosoft Excel(または [!DNL .xls][!DNL .xlsx])ファイルとして配布する場合は、アカウントにもMicrosoft Excelを実行する権限があることを確認します。

   1. アカウントのパスワードを入力し、確認します。
   1. クリック **[!UICONTROL OK]**.

1. サービスを右クリックし、 [!DNL Report Server] 指定したアカウ **[!UICONTROL Restart]** ントでサービスを再起動することを選択します。
1. 起動時にエラー [!DNL Report Server] が発生したかどうかを確認するには、///をク **[!UICONTROL Start]** リッ **[!UICONTROL Control Panel]** クし **[!UICONTROL Administrative Tools]** ます **[!UICONTROL Event Viewer]**。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. ウィンドウの左ペインで、「ア [!DNL Event Viewer] プリケーション」ログを選択します。
   1. 右側のウィンドウで、列に「Adobe」が含まれているイベントを探 [!DNL Source] します。
   1. アドビからエラーが見つかった場合は、エラーをダブルクリックしてウィンドウを表示し [!DNL Event Properties] ます。 このウィンドウには、エラーに関する詳細情報が表示されます。

      >[!NOTE]
      >
      >サービスの [!DNL Report Server] 開始後、Report Serverディレ [!DNL ReportServer.log] クトリにファイルが作成さ [!DNL Trace] れます。 このファイルは、の問題のトラブルシューティングにも役立ちま [!DNL Report Server]す。

のインストールが完了しまし [!DNL Report Server]た。 [!DNL Report Server] は、連続的に実行するように設計されています。 コンピューターを再起動すると、が自動的に再 [!DNL Report Server] 起動します。 手動で起動および停止する必要が [!DNL Report Server] ある場合は、Windowsのコントロールパネルを [!DNL Services] 使用して実行できます。
