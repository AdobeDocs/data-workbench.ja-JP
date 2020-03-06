---
description: ダッシュボードでデータを視覚化する各DPUには、Query APIライセンスが必要です。
solution: Analytics
title: クエリAPIの有効化を確認しています
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# クエリAPIの有効化を確認しています{#verifying-query-api-enablement}

ダッシュボードでデータを視覚化する各DPUには、Query APIライセンスが必要です。

以下に、Query APIがインストールされ、有効になっていることを検証する方法を示します。

1. Data Workbenchサーバーの証明書を検索します。
1. この証明書をテキストエディターで開きます。
1. 証明書に行が存在する `Product = Query API` ことを確認します。
1. フォルダ **[!UICONTROL Trace]** 内で、テキストエデ [!DNL InsightServer64.log] ィタでを開きます。
1. 最新の起動ログのエントリで、行が表示されていることを確認 `Enabling Query API (licensed)` します。

* Query APIが有効でない場合は、エントリが表示されます `Not enabling Query API (not licensed)`。
* ログエントリが見つからない場合や、Query APIの追加後にData Workbenchサーバーが再起動されたと思われる場合は、Data Workbenchサーバーを再起動し、ログを確認してください。

   Query APIが有効であることを検証できない場合は、Adobe ClientCareにお問い合わせください。
