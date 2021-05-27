---
description: レポートサーバーの登録と実行の手順です。
title: Windows サービスとしてのレポートサーバーの登録
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 9%

---

# Windows サービスとしてのレポートサーバーの登録{#registering-report-server-as-a-windows-service}

レポートサーバーの登録と実行の手順です。

この手順を実行する前に、[!DNL Report Server]サービスを実行するWindowsアカウントを特定します。 このアカウントに、生成されたレポートが格納される場所にアクセスするための適切な権限があることを確認します（つまり、[!DNL Local System Account]を使用しないでください）。

[!DNL Report Server]を起動するには、以下の手順に従います。 [!DNL Report Server]を初めて起動すると、Windowsサービスとして自動的に登録されます。

[!DNL Report Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

1. Windowsで、[!DNL Report Server]をインストールしたディレクトリに移動します。

   例：D:\Adobe\Report

1. ダブルクリック **[!UICONTROL ReportServer.exe]**.
1. [!DNL Report Server]が正しく実行されていることを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。
1. サービスリストで、[!DNL Report Server]のエントリを探し、そのステータスが「開始済み」で、起動タイプが「自動」であることを確認します。
1. [!DNL Report Server]を実行するユーザーアカウントを指定するには、次の操作を行います。

   1. **[!UICONTROL Report Server]**&#x200B;をダブルクリックして、[!DNL Properties]ウィンドウを開きます。

   1. 「**[!UICONTROL Log On]**」タブを選択します。
   1. **[!UICONTROL This account]**&#x200B;ラジオボタンを選択します。
   1. アカウント名を入力または参照します。 このアカウントには、生成されたレポートが保存される場所にアクセスする権限が必要です。

      >[!NOTE]
      >
      >[!DNL Report Server]がレポートをMicrosoft Excel（[!DNL .xls]または[!DNL .xlsx]）ファイルとして配信する場合は、アカウントにMicrosoft Excelを実行する権限も付与されていることを確認してください。

   1. アカウントのパスワードを入力し、確認します。
   1. 「**[!UICONTROL OK]**」をクリックします。

1. [!DNL Report Server]サービスを右クリックし、「**[!UICONTROL Restart]**」を選択して、指定したアカウントでサービスを再起動します。
1. 起動中に[!DNL Report Server]でエラーが発生したかどうかを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なる場合があります。

   1. [!DNL Event Viewer]ウィンドウの左側のペインで、「アプリケーション」ログを選択します。
   1. 右側のウィンドウの[!DNL Source]列で、Adobeを持つイベントを探します。
   1. Adobeでエラーが見つかった場合は、エラーをダブルクリックして[!DNL Event Properties]ウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

      >[!NOTE]
      >
      >[!DNL Report Server]サービスの開始後、[!DNL ReportServer.log]ファイルがレポートサーバーの[!DNL Trace]ディレクトリに作成されます。 このファイルは、[!DNL Report Server]の問題のトラブルシューティングにも役立ちます。

[!DNL Report Server]のインストールが完了しました。 [!DNL Report Server] は、連続して実行するように設計されています。コンピュータを再起動すると、[!DNL Report Server]が自動的に再起動します。 [!DNL Report Server]を手動で起動および停止する必要がある場合は、Windowsの[!DNL Services]コントロールパネルを使用して実行できます。
