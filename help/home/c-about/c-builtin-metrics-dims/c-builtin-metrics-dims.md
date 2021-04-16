---
description: この節では、Data Workbenchに用意されている組み込みの指標、ディメンション、フィルターについて詳しく説明します。
title: 組み込みの指標、ディメンション、フィルターについて
uuid: 05676254-f6f5-4cb1-a664-da96d5b965db
exl-id: d581a029-fd59-47c5-b832-64407102ace7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 8%

---

# 組み込みの指標、ディメンション、フィルターについて{#about-built-in-metrics-dimensions-and-filters}

この節では、Data Workbenchに用意されている組み込みの指標、ディメンション、フィルターについて詳しく説明します。

ほとんどすべての指標は、プロファイルのmetricsディレクトリに定義されます。 Insight Serverのログ処理設定ファイルと変換設定ファイルで定義されるログ処理と変換という2つの段階を通じて、データ処理の状況に関する技術情報を伝えるために、いくつかの組み込み指標が用意されています。

>[!NOTE]
>
>ログ処理段階では、すべてのイベントデータがログファイルから取得されるわけではありません。 場合によってはありますが、イベントデータはODBCデータソースなどの別のソースから取得される場合があります。 データソースについて詳しくは、『[データセット設定ガイド](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html)』を参照してください。
