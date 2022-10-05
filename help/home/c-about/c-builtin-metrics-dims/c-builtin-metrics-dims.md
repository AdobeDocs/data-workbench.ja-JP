---
description: この節では、Data Workbench に組み込まれている指標、ディメンション、フィルターについて詳しく説明します。
title: 組み込みの指標、ディメンション、フィルターについて
uuid: 05676254-f6f5-4cb1-a664-da96d5b965db
exl-id: d581a029-fd59-47c5-b832-64407102ace7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 8%

---

# 組み込みの指標、ディメンション、フィルターについて{#about-built-in-metrics-dimensions-and-filters}

{{eol}}

この節では、Data Workbench に組み込まれている指標、ディメンション、フィルターについて詳しく説明します。

ほとんどすべての指標は、プロファイルの metrics ディレクトリで定義されます。 Insight サーバーのログ処理設定ファイルと変換設定ファイルで定義されるログ処理と変換の 2 つの段階を通じて、データ処理の状態に関する技術情報を伝えるために、いくつかの組み込み指標が用意されています。

>[!NOTE]
>
>ログ処理段階では、すべてのイベントデータがログファイルから送信されるわけではありません。 場合によってはありますが、イベントデータは ODBC データソースなどの別のソースから取得することができます。 データソースについて詳しくは、 [データセット設定ガイド](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html).
