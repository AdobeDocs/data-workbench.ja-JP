---
description: ダッシュボードを操作する前に、SQL Serverへのアクセスを許可する必要があります。
solution: Analytics
title: SQL Serverの設定
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# SQL Serverの設定{#configuring-the-sql-server}

ダッシュボードを操作する前に、SQL Serverへのアクセスを許可する必要があります。

1. SQL Management Studioを管理者として開きます。
1. 右クリックして選択し、新しいログインを **[!UICONTROL Logins]** 追加しま **[!UICONTROL New Login]**&#x200B;す。
1. 完全なアプリケーションプールID名を入力します。

   デフォルトでは、アプリケーションプールIDはアプリケーションプールの名前に従って命名されます。 選択した場 `dashboard`合は、IDに名前が付けられま `IIS AppPool\dashboard`す。 1.ロールを **[!UICONTROL Server Roles]** 選択してチェック **[!UICONTROL dbcreator]** します。
1. Click **[!UICONTROL OK]** to add the new user.
