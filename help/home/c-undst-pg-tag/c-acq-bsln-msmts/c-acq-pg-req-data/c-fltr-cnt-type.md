---
description: Sensorのコンテンツタイプのフィルタリング機能の目的は、分析に役立たない情報を保存し処理する必要がないことです。
title: コンテンツタイプによるフィルタリング
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# コンテンツタイプによるフィルタリング{#filtering-by-content-type}

Sensorのコンテンツタイプのフィルタリング機能の目的は、分析に役立たない情報を保存し処理する必要がないことです。

WebサーバーのAPIを通じて利用できる要求データの多くは、ビジネス分析では役に立ちません。 ストレージと処理は高価で、[!DNL Sensor’s]コンテンツタイプのフィルタリングを行うことで、不要なストレージや処理を回避できます。

[!DNL Site]は、特定のリストのコンテンツタイプ（カスケードスタイルシート、イメージリクエストなど）を除き、[!DNL Sensor]がdata workbenchサーバーに送信する前に除外する、すべてのWebコンテンツタイプリクエストの測定データ（リクエストデータ、ログエントリ、ログデータなど）を取得します。 このフィルタリングはWebサーバー全体に対して無効にでき、特定の埋め込みオブジェクトのクエリ文字列に名前と値のペア「Log=1」を追加することで、特定のコンテンツオブジェクトに対して上書きすることもできます（例：[!DNL http://www.mysite.com/advertisement.gif?Log=1]）。
