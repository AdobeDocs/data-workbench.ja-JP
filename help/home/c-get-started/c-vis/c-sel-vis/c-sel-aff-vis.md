---
description: ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。
solution: Analytics
title: 選択による他のビジュアライゼーションへの影響について
topic: Data workbench
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 選択による他のビジュアライゼーションへの影響について{#understanding-how-a-selection-affects-other-visualizations}

ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。

選択を行うと、Data Workbenchは、クエリーの結果をフィルタリングして、ワークスペース内のビジュアライゼーションを生成します。 具体的なフィルターは、ビジュアライゼーションごとに異なります。

次の例では、Data Workbenchが3種類のビジュアライゼーションに選択を適用する方法を示します。 これらの例を確認すると、ビジュアライゼーションに対する選択のフィルタリング効果がわかります。また、フィルタリングされたビジュアライゼーションに表示される結果の解釈方法についても説明します。

* [Sessions 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Visitors 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Sessions 指標でビジュアライゼーションをフィルタリングする {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

In this example, the [!DNL /direct.asp/?ldPage=hme] URI in the visualization on the left is filtering the metric for Sessions displayed in the visualization on the right.

![](assets/client-vis1.png)

* **クエリーに対する選択の効果：** Data Workbenchは、選択したURIのセッションをフィルタリングします。 In this example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] element is filtered as follows:

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **ビジュアライゼーションの解釈：** フィルター適用済みのビジュアライゼーションは、ビジュアライゼーションにリストされたURIを含むセッションの数とを表しま [!DNL /direct.asp/?ldPage=hme]す。 This example shows that there were 1,113 sessions during which visitors viewed both [!DNL /pops/disclosure_pop.asp] page and [!DNL /direct.asp/?ldPage=hme] in the same session.

## Visitors 指標でビジュアライゼーションをフィルタリングする {#section-97d38c7f03e8457189a9c72d69514ed2}

In this example, the [!DNL /direct.asp/?ldPage=home] URI in the visualization on the left is filtering the metric for Visitors in the visualization on the right.

![](assets/client-vis2.png)

* **クエリーに対する選択の効果：** Data Workbenchは、選択したURIに対して訪問者をフィルタリングします。 In this example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] URI is filtered as follows:

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションおよび（同じセッション中に限らないが） [!DNL /direct.asp/?ldPage=hme] リストされたURIを表示した訪問者を表します。 The example above shows that 2,041 visitors have viewed both [!DNL /pops/disclosure_pop.asp] and [!DNL /direct.asp/?ldPage=hme].

## Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする {#section-f746182311d648dcb98716b0fe846e25}

In this example, the [!DNL /direct.asp/?ldPage=hme] URI in the visualization on the left is filtering the metric for visitor-by-session in the visualization on the right.

![](assets/client-vis3.png)

* **クエリーに対する選択の効果：** Data Workbenchは、選択したURIに対して、セッション別の訪問者をフィルタリングします。 For example, the query that generates the value for the [!DNL /pops/disclosure_pop.asp] URI is filtered as follows:

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションにリストされたURIと同じセッション中に両方のURIを表 [!DNL /direct.asp/?ldPage=hme] 示した訪問者を表します。 This example shows that 1,069 visitors saw both [!DNL /pops/disclosure_pop.asp] and [!DNL /direct.asp/?ldPage=hme] during a single session.

