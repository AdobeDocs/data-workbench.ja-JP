---
description: ダッシュボードを操作する前に、SQL Serverへのアクセスを許可する必要があります。
title: SQL Server の設定
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# SQL Server の設定{#configuring-the-sql-server}

ダッシュボードを操作する前に、SQL Serverへのアクセスを許可する必要があります。

1. SQL Management Studioを管理者として開きます。
1. **[!UICONTROL Logins]**&#x200B;を右クリックし、**[!UICONTROL New Login]**&#x200B;を選択して、新しいログインを追加します。
1. 完全なアプリケーションプールID名を入力します。

   デフォルトでは、アプリケーションプールのIDは、アプリケーションプールの名前にちなんで指定されます。 `dashboard`を選択した場合、IDは`IIS AppPool\dashboard`という名前になります。 1. **[!UICONTROL Server Roles]**&#x200B;を選択し、**[!UICONTROL dbcreator]**&#x200B;の役割を確認します。
1. **[!UICONTROL OK]**&#x200B;をクリックして、新しいユーザーを追加します。
