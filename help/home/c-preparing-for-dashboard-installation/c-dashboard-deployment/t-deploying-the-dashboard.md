---
description: IISでダッシュボードを展開する手順です。
solution: Analytics
title: ダッシュボードのデプロイ
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ダッシュボードのデプロイ{#deploying-the-dashboard}

IISでダッシュボードを展開する手順です。

1. ダッシュボードをインストールするインストールフォルダを作成します(例： [!DNL c:\inetpub\wwwroot\dashboard])。
1. IISでダッシュボードのアプリケーションプールを作成します。
1. IISマネージャコンソールを開きます。
1. Go to **[!UICONTROL Application Pools]**.
1. 右側のメニューで**[!UICONTROL Add Application Pool…]** **[!UICONTROL Actions]** を選択します。
1. フォーム **[!UICONTROL Add Application Pool]** で、ダッシュボードを名前に使用し、.NET Framework V.4.0.xxxxxを.NET Framework Versionとして選択します。
1. 他のフィールドはデフォルトのままにし、をクリックしてア **[!UICONTROL OK]** プリケーションプールを作成します。
1. ダッシュボードアプリケーションをデプロイします。
1. IISマネージャコンソールを開きます。
1. を展開す **[!UICONTROL Default Web Site]**&#x200B;ると、c:\inetpub\wwwroot\dashboard by defaultで作成したフォルダが表示されます。
1. フォルダを右クリックし、を選択しま **[!UICONTROL Convert to Application]**&#x200B;す。
1. 手順2で作成した**[!UICONTROL Application Pool]**（「ダッシュボード」など）を選択します。
1. 展開 **[!UICONTROL Sites]**&#x200B;先のWebサイト（例：「デフォルトのWebサイト」）を右クリックします。
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. アドビが提供するダッシュボード展開ファイルを参照して選択します。
1. を2回ク **[!UICONTROL Next]** リックして、「Enter Application Information」画面に進みます。
1. この画面で、ダッシュボードの展開をカスタマイズできます。
1. [ ]に、 **[!UICONTROL Application Path]**&#x200B;前に選択したフォルダ名を入力します。
1. 新しいイ **[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;ンストー `False`ルの場合は、を入力します。
1. 必要に応じて、接続文字列をカスタマイズします。 次に例を示します。

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. をクリック **[!UICONTROL Next]** すると、IISがアプリケーションのインストールを開始します。
1. インストールが完了したら、インストールログにエラーは表示されません。
