---
description: レポートサーバーの登録と実行の手順です。
title: Windows サービスとしてのレポートサーバーの登録
uuid: 01fc0bbf-9f4a-487e-b1cb-16bf6974a541
exl-id: 46ea5dd4-7041-451e-91e5-f927873fc7d7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 9%

---

# Windows サービスとしてのレポートサーバーの登録{#registering-report-server-as-a-windows-service}

{{eol}}

レポートサーバーの登録と実行の手順です。

この手順を実行する前に、Windows アカウントを特定し、 [!DNL Report Server] サービスが実行されます。 このアカウントに、生成されたレポートが格納される場所にアクセスするための適切な権限があることを確認します ( つまり、 [!DNL Local System Account]) をクリックします。

以下の手順を使用して開始します。 [!DNL Report Server]. 開始時 [!DNL Report Server] 初めて、Windows サービスとして自身を自動的に登録します。

[!DNL Report Server] を初めて起動すると、デジタル証明書を登録するために、Adobe License Server に自動的に接続されます。登録プロセスを正常に完了するには、次の手順を実行する際に、コンピューターがインターネットに接続されている必要があります。

1. Windows で、をインストールしたディレクトリに移動します。 [!DNL Report Server].

   例：D:\Adobe\Report

1. ダブルクリック **[!UICONTROL ReportServer.exe]**.
1. 次の手順で確認します。 [!DNL Report Server] が正しく実行されている場合は、「 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。
1. サービスリストで、 [!DNL Report Server] 「開始済み」で、起動タイプが「自動」であることを確認します。
1. 次の手順を実行して、のユーザーアカウントを指定します。 [!DNL Report Server] を実行します。

   1. ダブルクリック **[!UICONTROL Report Server]** 開く [!DNL Properties] ウィンドウ

   1. を選択します。 **[!UICONTROL Log On]** タブをクリックします。
   1. を選択します。 **[!UICONTROL This account]** ラジオボタン。
   1. アカウント名を入力または参照します。 このアカウントには、生成されたレポートが保存される場所にアクセスする権限が必要です。

      >[!NOTE]
      >
      >If [!DNL Report Server] はレポートをMicrosoft Excel ( [!DNL .xls] または [!DNL .xlsx]) ファイルの場合は、アカウントにMicrosoft Excel を実行する権限もあることを確認してください。

   1. アカウントのパスワードを入力し、確認します。
   1. 「**[!UICONTROL OK]**」をクリックします。

1. を右クリックします。 [!DNL Report Server] サービスと選択 **[!UICONTROL Restart]** 指定したアカウントでサービスを再開します。
1. 次の手順で、 [!DNL Report Server] 起動時にエラーが発生した場合は、「 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. このコマンドの順序は、使用している Windows のバージョンによって異なる場合があります。

   1. の左側のペイン [!DNL Event Viewer] ウィンドウで、「アプリケーション・ログ」を選択します。
   1. 右側のウィンドウで、「 [!DNL Source] 列。
   1. エラーがAdobeから見つかった場合は、エラーをダブルクリックして [!DNL Event Properties] ウィンドウ このウィンドウには、エラーに関する詳細情報が表示されます。

      >[!NOTE]
      >
      >次の期間の後 [!DNL Report Server] サービスが開始すると、ファイル [!DNL ReportServer.log] が Report Server で作成された [!DNL Trace] ディレクトリ。 このファイルは、 [!DNL Report Server].

のインストールが完了しました [!DNL Report Server]. [!DNL Report Server] は、継続的に実行するように設計されています。 マシンを再起動した場合、 [!DNL Report Server] が自動的に再起動します。 を起動および停止する必要がある場合 [!DNL Report Server] 手動で、 [!DNL Services] Windows のコントロールパネル
