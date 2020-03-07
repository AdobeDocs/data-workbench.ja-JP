---
description: Sensorのコンテンツタイプのフィルタリング機能の目的は、分析に役立たない情報を保存し、処理する必要をなくすことです。
solution: Analytics
title: コンテンツタイプでのフィルタリング
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# コンテンツタイプでのフィルタリング{#filtering-by-content-type}

Sensorのコンテンツタイプのフィルタリング機能の目的は、分析に役立たない情報を保存し、処理する必要をなくすことです。

WebサーバーのAPIを通じて利用できる要求データの多くは、ビジネス分析には役立ちません。 保存と処理は高価で、コンテンツタ [!DNL Sensor’s] イプのフィルタリングにより、不要な保存と処理を回避できます。

Webログデータの処理性能を最大化し、保存する必要のある測定データ量を減らすため、特別にリストされたコンテンツタイプ（カスケードスタイルシート、画像要求など）を除くすべてのWebコンテンツタイプの要求の測定データ（要求データ、ログエントリ、ログデータなど）を取得します [!DNL Site][!DNL Sensor]。 このフィルタリングは、Webサーバー全体に対して無効にすることができます。また、特定の埋め込みオブジェクトのクエリ文字列に名前と値のペア「Log=1」を追加することで、特定のコンテンツオブジェクトに対して上書きすることもできます(例： [!DNL http://www.mysite.com/advertisement.gif?Log=1])。
