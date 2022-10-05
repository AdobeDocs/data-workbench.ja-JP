---
description: データを視覚化するためのダッシュボードにある各 DPU には、クエリ API ライセンスが必要です。
title: クエリ API 有効化の確認
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# クエリ API 有効化の確認{#verifying-query-api-enablement}

{{eol}}

データを視覚化するためのダッシュボードにある各 DPU には、クエリ API ライセンスが必要です。

以下に、クエリ API がインストールされ、有効になっていることを検証する方法の説明を示します。

1. Data Workbench サーバーの証明書を検索します。
1. この証明書をテキストエディターで開きます。
1. 行が `Product = Query API` が証明書に存在します。
1. 内 **[!UICONTROL Trace]** フォルダーを開き、 [!DNL InsightServer64.log] をクリックします。
1. 最新の起動ログエントリで、次の行が `Enabling Query API (licensed)` が表示されます。

* クエリ API が有効になっていない場合は、エントリが表示されます `Not enabling Query API (not licensed)`.
* ログエントリが表示されない場合や、Query API の追加後に Data Workbench サーバーが再起動されたと思われる場合は、Data Workbench サーバーを再起動し、ログを確認してください。

   クエリ API が有効になっていることを検証できない場合は、AdobeClientCare にお問い合わせください。
