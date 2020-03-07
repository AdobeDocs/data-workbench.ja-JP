---
description: 詳細テーブルを使用すると、他のビジュアライゼーション内に作成した選択範囲により定義されるデータのサブセットに関する追加情報を表示できます。
solution: Analytics
title: 詳細テーブル
topic: Data workbench
uuid: 2becff5e-c78d-4ac7-8cda-814ad0193efd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Detail table{#detail-table}

詳細テーブルを使用すると、他のビジュアライゼーション内に作成した選択範囲により定義されるデータのサブセットに関する追加情報を表示できます。

表示される追加情報は、すべての利用可能データをサンプリングしたものです。

![](assets/vis_details.png)

以下の表は、詳細テーブルの要素について説明したものです。

<table id="table_C88C7F7F5AEA4820B908923E45CC0A62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col02" class="entry"> 色 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>レベル </p> </td> 
   <td colname="col02"> <p>ピンク </p> </td> 
   <td colname="col2"> <p>詳細な属性および指標の情報を表示する可算ディメンション。レベルの前には、利用可能な要素数に対して表示される要素数が付きます。例えば、6/444 は、444 の利用可能な要素のうち 6 つの要素が表示されるということを示しています。上記の例で、Visitors というレベルは、表示される詳細のすべてが訪問者に基づいているということを示します。Page Views というレベルは、表示される詳細のすべてがページビューに基づいているということを示します。複数のレベルを同時に表示することは、様々な可算の親を持つデータを分析する場合に役立ちます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>属性 </p> </td> 
   <td colname="col02"> <p>緑 </p> </td> 
   <td colname="col2"> <p>City 対 Visitors など、レベルと 1 対多または 1 対 1 のディメンション。各行には、選択したレベルの各要素に関連付けられた要素が表示されます。上記の例で、Domain 属性と City 属性には、各サンプル訪問者のドメインと都市がリストされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指標 </p> </td> 
   <td colname="col02"> <p>青 </p> </td> 
   <td colname="col2"> <p>選択したレベルに関する指標の詳細。レベルが Visitors に設定されている上記の例で、Page Views 指標には個々の訪問者のページビュー数が表示され、Page Views レベルには各ページビューの詳細が表示されます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Web サイトデータを扱っていて、特定の都市または特定のドメインからの訪問者が特定の期間に訪問したページを識別したいとします。

まず、関心がある期間を表示するビジュアライゼーションを作成してから、その期間を選択する必要があります。これで、データセット内のサンプル人数分の訪問者に関する目的のデータを表示する詳細テーブルを追加できます。

上述の詳細を表示するには、以下の手順を実行する必要があります。

1. 詳細テーブル内で右クリックし、/をクリッ **[!UICONTROL Add Level]** クしま **[!UICONTROL Visitor]**&#x200B;す。
1. 詳細テーブル内で右クリックし、/をクリッ **[!UICONTROL Add Level]** クしま **[!UICONTROL Page View]**&#x200B;す。
1. レベルの見出しを右ク **[!UICONTROL Visitors]** リックし、//をク **[!UICONTROL Add Attribute]** リック **[!UICONTROL Geography]** しま **[!UICONTROL Domain]**&#x200B;す。
1. Visitorsレベルの見出し内で右クリックし、//をク **[!UICONTROL Add Attribute]** リッ **[!UICONTROL Geography]** クしま **[!UICONTROL City]**&#x200B;す。
1. Visitorsレベルの見出し内で右クリックし、/をクリッ **[!UICONTROL Add Metric]** クしま **[!UICONTROL Page Views]**&#x200B;す。
1. ページビュー数レベルの見出し内で右クリックし、//をク **[!UICONTROL Add Attribute]** リック **[!UICONTROL Page]** しま **[!UICONTROL Page]**&#x200B;す。

次のワークスペースの例は、指定した期間中のサイトへの訪問者をランダムサンプリングした 6 人の訪問者に関連する詳細を示しています。

![](assets/client-tab1.png)

## レベルの追加 {#section-f948d3361fd84906ac4d9ebce520bfd0}

* 詳細テーブル内で右クリックし、/&lt;> **[!UICONTROL Add Level]** をクリ *ック&#x200B;**[!UICONTROL dimension name]**します*。

![](assets/mnu_DetailsTable_AddLevel.png)

## レベルの削除 {#section-a8c820e0b656451e98e5ea75373edefc}

* 既存のレベルの見出しを右クリックし、/&lt;> **[!UICONTROL Remove Level]** をク *リッ&#x200B;**[!UICONTROL dimension name]**クします*。

![](assets/mnu_DetailsTable_Level.png)

## Add attributes and metrics {#section-cdda2df3c9a448d5b9770686c8b8efb3}

* 属性または指標の見出しを右クリックし、 **[!UICONTROL Add Attribute]** /&lt;> */&lt;**[!UICONTROL attribute name]**>また* は **[!UICONTROL Add Metric]** &lt; ***[!UICONTROL metric name]***>をクリックします。

![](assets/mnu_DetailsTable.png)

## 属性と指標の削除 {#section-4002ac957a2846678f9940270987d651}

* 削除する列を右クリックし、「>&lt;>」または「 **[!UICONTROL Remove Attribute]** &lt; *>**[!UICONTROL attribute name]**」を* クリッ **[!UICONTROL Remove Metric]*****[!UICONTROL metric name]***&#x200B;クします。

![](assets/mnu_DetailsTable.png)

## Microsoft Excelにエクスポート {#section-a9eaba63c88a4598836a34669ba8cac1}

ウィンドウの書き出しの詳細については、「ウィンドウデータの書き [出し」を参照してくださ](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)い。
