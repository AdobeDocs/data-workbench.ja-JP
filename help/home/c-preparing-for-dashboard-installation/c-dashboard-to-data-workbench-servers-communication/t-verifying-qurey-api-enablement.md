---
description: データを視覚化するためのダッシュボードの各DPUには、クエリAPIライセンスが必要です。
title: クエリ API 有効化の確認
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# クエリ API 有効化の確認{#verifying-query-api-enablement}

データを視覚化するためのダッシュボードの各DPUには、クエリAPIライセンスが必要です。

以下に、クエリAPIがインストールされ有効になっていることを検証する方法の説明を示します。

1. Data Workbenchサーバーの証明書を検索します。
1. この証明書をテキストエディターで開きます。
1. 証明書に`Product = Query API`行が存在することを確認します。
1. **[!UICONTROL Trace]**&#x200B;フォルダーで、 [!DNL InsightServer64.log]をテキストエディターで開きます。
1. 最新の起動ログエントリで、`Enabling Query API (licensed)`行が表示されることを確認します。

* クエリAPIが有効になっていない場合は、「`Not enabling Query API (not licensed)`」というエントリが表示されます。
* ログエントリが表示されない場合や、クエリAPIの追加後にData Workbenchサーバーが再起動されたと思われる場合は、Data Workbenchサーバーを再起動してログを確認してください。

   クエリAPIが有効になっていることを検証できない場合は、AdobeのClientCareにお問い合わせください。
