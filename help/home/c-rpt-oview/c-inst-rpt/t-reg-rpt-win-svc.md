---
description: Report Serverを登録して実行する手順です。
title: Windows サービスとしてのレポートサーバーの登録
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 9%

---

# Windows サービスとしてのレポートサーバーの登録{#registering-report-server-as-a-windows-service}

Report Serverを登録して実行する手順です。

この手順を実行する前に、[!DNL Report Server]サービスを実行するWindowsアカウントを指定します。 生成されたレポートが保存されている場所にアクセスする適切な権限がこのアカウントにあることを確認してください（つまり、[!DNL Local System Account]を使用しないでください）。

次の手順で[!DNL Report Server]を開始します。 [!DNL Report Server]を初めて開始すると、Windowsサービスとして自動的に登録されます。

[!DNL Report Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

1. Windowsで、[!DNL Report Server]をインストールしたディレクトリに移動します。

   例：D:\Adobe\Report

1. ダブルクリック **[!UICONTROL ReportServer.exe]**.
1. [!DNL Report Server]が正しく実行されていることを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。
1. サービスリストで、[!DNL Report Server]のエントリを探し、ステータスが「開始」で、起動タイプが「自動」であることを確認します。
1. [!DNL Report Server]を実行するユーザーアカウントを指定するには、次の手順を実行します。

   1. **[!UICONTROL Report Server]**&#x200B;を重複クリックして[!DNL Properties]ウィンドウを開きます。

   1. 「**[!UICONTROL Log On]**」タブを選択します。
   1. **[!UICONTROL This account]**&#x200B;ラジオボタンを選択します。
   1. アカウント名を入力または参照します。 このアカウントには、生成されたレポートが保存されている場所へのアクセス権が必要です。

      >[!NOTE]
      >
      >[!DNL Report Server]がレポートをMicrosoft Excel （ [!DNL .xls]または[!DNL .xlsx]）ファイルとして配布する場合は、アカウントにもMicrosoft Excelを実行する権限があることを確認してください。

   1. アカウントのパスワードを入力し、確認します。
   1. 「**[!UICONTROL OK]**」をクリックします。

1. [!DNL Report Server]サービスを右クリックし、**[!UICONTROL Restart]**&#x200B;を選択して、指定したアカウントでサービスを再起動します。
1. 開始のアップ中に[!DNL Report Server]でエラーが発生したかどうかを確認するには、**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**&#x200B;をクリックします。 このコマンドの順序は、使用しているWindowsのバージョンによって異なります。

   1. [!DNL Event Viewer]ウィンドウの左ペインで、「Applications log」を選択します。
   1. 右側のウィンドウで、[!DNL Source]列にAdobeのあるイベントを探します。
   1. Adobeからエラーが見つかった場合は、重複を押しながらエラーをクリックして[!DNL Event Properties]ウィンドウを表示します。 このウィンドウには、エラーに関する詳細情報が表示されます。

      >[!NOTE]
      >
      >[!DNL Report Server]サービス開始の後に、[!DNL ReportServer.log]ファイルがReport Server [!DNL Trace]ディレクトリに作成されます。 このファイルは[!DNL Report Server]の問題のトラブルシューティングにも役立ちます。

[!DNL Report Server]のインストールが完了しました。 [!DNL Report Server] は、連続的に実行するように設計されています。マシンを再起動すると、[!DNL Report Server]が自動的に再起動します。 [!DNL Report Server]を手動で開始して停止する必要がある場合は、Windowsの[!DNL Services]コントロールパネルを使用して実行できます。
