---
description: IISでダッシュボードをデプロイする手順です。
title: ダッシュボードのデプロイ
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# ダッシュボードのデプロイ{#deploying-the-dashboard}

IISでダッシュボードをデプロイする手順です。

1. [!DNL c:\inetpub\wwwroot\dashboard]など、ダッシュボードをインストールするインストールフォルダーを作成します。
1. IISでダッシュボードのアプリケーションプールを作成します。
1. IISマネージャーコンソールを開きます。
1. **[!UICONTROL Application Pools]** にアクセスします。
1. 右側の&#x200B;**[!UICONTROL Actions]**&#x200B;メニューで「**[!UICONTROL Add Application Pool…]**」を選択します。
1. **[!UICONTROL Add Application Pool]**&#x200B;フォームで、名前のダッシュボードを使用し、 .NET Frameworkのバージョンとして「 .NET Framework v.4.0.xxxxxx 」を選択します。
1. 他のフィールドはデフォルトのままにし、**[!UICONTROL OK]**&#x200B;をクリックしてアプリケーションプールを作成します。
1. ダッシュボードアプリケーションをデプロイします。
1. IISマネージャーコンソールを開きます。
1. **[!UICONTROL Default Web Site]**&#x200B;を展開すると、c:\inetpub\wwwroot\dashboard by defaultで作成したフォルダーが表示されます。
1. フォルダーを右クリックし、「**[!UICONTROL Convert to Application]**」を選択します。
1. 手順2で作成した**[!UICONTROL Application Pool]**（「ダッシュボード」など）を選択します。
1. **[!UICONTROL Sites]**&#x200B;の下で、デプロイするWebサイト（「デフォルトのWebサイト」など）を右クリックします。
1. 選択 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. ダッシュボードで提供されたダッシュボード展開ファイルを参照し、Adobeします。
1. **[!UICONTROL Next]**&#x200B;を2回クリックして、 Enter Application Information画面に進みます。
1. この画面から、ダッシュボードのデプロイメントをカスタマイズできます。
1. **[!UICONTROL Application Path]**&#x200B;には、前に選択したフォルダー名を入力します。
1. **[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;の下に、`False`と入力します。これは新しいインストールです。
1. 必要に応じて、接続文字列をカスタマイズします。 次に例を示します。

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. **[!UICONTROL Next]**&#x200B;をクリックすると、IISがアプリケーションのインストールを開始します。
1. インストールが完了したら、インストールログにエラーは表示されません。
