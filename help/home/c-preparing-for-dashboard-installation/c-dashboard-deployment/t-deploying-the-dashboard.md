---
description: IIS でダッシュボードをデプロイする手順です。
title: ダッシュボードのデプロイ
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# ダッシュボードのデプロイ{#deploying-the-dashboard}

{{eol}}

IIS でダッシュボードをデプロイする手順です。

1. ダッシュボードをインストールするインストールフォルダーを作成します（例： ）。 [!DNL c:\inetpub\wwwroot\dashboard].
1. IIS でダッシュボードのアプリケーションプールを作成します。
1. IIS Manager コンソールを開きます。
1. **[!UICONTROL Application Pools]** にアクセスします。
1. 選択**[!UICONTROL Add Application Pool…]** **[!UICONTROL Actions]** メニューを右に表示します。
1. 内 **[!UICONTROL Add Application Pool]** フォームで、名前のダッシュボードを使用し、 .NET Framework のバージョンとして「 .NET Framework v.4.0.xxxxxx 」を選択します。
1. 他のフィールドをデフォルトのままにし、「 **[!UICONTROL OK]** をクリックして、アプリケーションプールを作成します。
1. ダッシュボードアプリケーションをデプロイします。
1. IIS Manager コンソールを開きます。
1. を展開します。 **[!UICONTROL Default Web Site]**&#x200B;をクリックした場合は、 c:\inetpub\wwwroot\dashboard by defaultで作成したフォルダーが表示されます。
1. フォルダーを右クリックし、「 」を選択します。 **[!UICONTROL Convert to Application]**.
1. **[!UICONTROL Application Pool]**手順 2 で作成（「ダッシュボード」など）。
1. の下 **[!UICONTROL Sites]**&#x200B;をクリックし、デプロイする Web サイト（例：「デフォルトの Web サイト」）を右クリックします。
1. 選択 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. ダッシュボードで提供されたダッシュボード展開ファイルを参照してAdobeします。
1. クリック **[!UICONTROL Next]** を 2 回クリックして、[Enter Application Information] 画面に進みます。
1. この画面から、ダッシュボードのデプロイメントをカスタマイズすることを選択できます。
1. の場合 **[!UICONTROL Application Path]**」で、以前に選択したフォルダー名を入力します。
1. の下 **[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;を入力して、 `False`新しいインストールなので、
1. 必要に応じて、接続文字列をカスタマイズします。 次に例を示します。

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. クリック **[!UICONTROL Next]** と IIS がアプリケーションのインストールを開始します。
1. インストールが完了したら、インストールログにエラーは表示されません。
