---
description: ダッシュボードを操作する前に、SQL Server へのアクセスを許可する必要があります。
title: SQL Server の設定
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# SQL Server の設定{#configuring-the-sql-server}

{{eol}}

ダッシュボードを操作する前に、SQL Server へのアクセスを許可する必要があります。

1. SQL Management Studio を管理者として開きます。
1. 右クリックして新しいログインを追加 **[!UICONTROL Logins]** および選択 **[!UICONTROL New Login]**.
1. 完全なアプリケーションプール ID 名を入力します。

   デフォルトでは、アプリケーションプールの ID は、アプリケーションプールの名前にちなんで名前が付けられます。 次を選択した場合： `dashboard`の場合、id は `IIS AppPool\dashboard`. 1. 「 」を選択します。 **[!UICONTROL Server Roles]** そして、 **[!UICONTROL dbcreator]** 役割。
1. クリック **[!UICONTROL OK]** をクリックして、新しいユーザーを追加します。
