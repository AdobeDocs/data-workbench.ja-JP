---
description: このダッシュボード製品には、AdobeのClientCareが提供するライセンスが必要です。
title: ダッシュボードライセンスキーの追加
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# ダッシュボードライセンスキーの追加{#add-dashboard-license-key}

このダッシュボード製品には、AdobeのClientCareが提供するライセンスが必要です。

1. 管理者として&#x200B;**[!UICONTROL SQL Management Studio]**&#x200B;を開きます。
1. ダッシュボードが作成したデータベース（たとえば、thinclientdb）を開きます。
1. **[!UICONTROL Configuration]**&#x200B;テーブルを右クリックし、**[!UICONTROL Edit Top 200 Rows]**&#x200B;をクリックします。
1. **[!UICONTROL licenseKey]**&#x200B;フィールドを探し、AdobeのClientCareから提供されたキーを&#x200B;**[!UICONTROL Value]**&#x200B;列に入力します。
1. **[!UICONTROL IIS Manager Console]**&#x200B;の&#x200B;**[!UICONTROL Application Pool]**&#x200B;を再起動します。
