---
description: この節では、Data Workbenchに組み込まれている指標、ディメンション、フィルターについて詳しく説明します。
title: 組み込みの指標、ディメンション、フィルターについて
uuid: 05676254-f6f5-4cb1-a664-da96d5b965db
exl-id: d581a029-fd59-47c5-b832-64407102ace7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 8%

---

# 組み込みの指標、ディメンション、フィルターについて{#about-built-in-metrics-dimensions-and-filters}

この節では、Data Workbenchに組み込まれている指標、ディメンション、フィルターについて詳しく説明します。

ほとんどすべての指標は、プロファイルのmetricsディレクトリで定義されます。 いくつかの組み込み指標が提供され、ログ処理と変換という2つの段階を通じてデータ処理の状態に関する技術情報を伝えます。これらは、Insightサーバーのログ処理設定ファイルと変換設定ファイルでそれぞれ定義されます。

>[!NOTE]
>
>ログ処理段階では、すべてのイベントデータがログファイルから送信されるわけではありません。 場合によってはありますが、イベントデータはODBCデータソースなどの別のソースから取得される場合があります。 データソースについて詳しくは、『[データセット設定ガイド](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html)』を参照してください。
