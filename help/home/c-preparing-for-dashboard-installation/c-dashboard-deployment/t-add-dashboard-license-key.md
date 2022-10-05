---
description: このダッシュボード製品には、AdobeClientCare が提供するライセンスが必要です。
title: ダッシュボードライセンスキーの追加
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# ダッシュボードライセンスキーの追加{#add-dashboard-license-key}

{{eol}}

このダッシュボード製品には、AdobeClientCare が提供するライセンスが必要です。

1. 開く **[!UICONTROL SQL Management Studio]** 管理者として。
1. ダッシュボードで作成したデータベース（thinclientdb など）を開きます。
1. を右クリックします。 **[!UICONTROL Configuration]** テーブルとクリック **[!UICONTROL Edit Top 200 Rows]**.
1. 次を検索： **[!UICONTROL licenseKey]** フィールドに入力し、AdobeClientCare から提供されたキーを **[!UICONTROL Value]** 列。
1. を再起動します。 **[!UICONTROL Application Pool]** 内 **[!UICONTROL IIS Manager Console]**.
