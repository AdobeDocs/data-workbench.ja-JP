---
description: ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。
title: 選択による他のビジュアライゼーションへの影響について
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 26%

---

# 選択による他のビジュアライゼーションへの影響について{#understanding-how-a-selection-affects-other-visualizations}

ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。

選択を行うと、Data Workbenchフィルターは、ワークスペース内のビジュアライゼーションの生成に使用されるクエリの結果を選択します。 具体的なフィルターは、ビジュアライゼーションごとに異なります。

以下の例では、Data Workbenchが3種類のビジュアライゼーションに選択を適用する方法を示します。 これらの例を確認すると、ビジュアライゼーションに対する選択のフィルタリング効果がわかります。また、フィルタリングされたビジュアライゼーションに表示される結果の解釈方法についても説明します。

* [Sessions 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Visitors 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Sessions 指標でビジュアライゼーションをフィルタリングする  {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=hme] URIによって、右側のビジュアライゼーションに表示されているセッションの指標がフィルタリングされています。

![](assets/client-vis1.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIのセッションをフィルターします。この例では、[!DNL /pops/disclosure_pop.asp]要素の値を生成するクエリが次のようにフィルタリングされます。

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **ビジュアライゼーションの解釈：フィルタ** ー適用されたビジュアライゼーションは、ビジュアライゼーションにリストされたURIと、を含むセッションの数を表し [!DNL /direct.asp/?ldPage=hme]ます。この例では、訪問者が同じセッション内で[!DNL /pops/disclosure_pop.asp]ページと[!DNL /direct.asp/?ldPage=hme]の両方を表示したセッションが1,113個あったことを示しています。

## Visitors 指標でビジュアライゼーションをフィルタリングする {#section-97d38c7f03e8457189a9c72d69514ed2}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=home] URIによって、右側のビジュアライゼーションの訪問者の指標がフィルタリングされています。

![](assets/client-vis2.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIの訪問者をフィルターします。この例では、[!DNL /pops/disclosure_pop.asp] URIの値を生成するクエリが次のようにフィルタリングされます。

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションに一覧表示されたURIと [!DNL /direct.asp/?ldPage=hme] （同じセッション中に限らず）を表示した訪問者を表します。上の例では、2,041人の訪問者が[!DNL /pops/disclosure_pop.asp]と[!DNL /direct.asp/?ldPage=hme]の両方を表示したことがわかります。

## Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする {#section-f746182311d648dcb98716b0fe846e25}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=hme] URIによって、右側のビジュアライゼーションのセッション別訪問者の指標がフィルタリングされています。

![](assets/client-vis3.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIに対する訪問者をセッション別にフィルターします。例えば、[!DNL /pops/disclosure_pop.asp] URIの値を生成するクエリは、次のようにフィルタリングされます。

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションに一覧表示されたURIと同じセッション [!DNL /direct.asp/?ldPage=hme] 中に表示されたURIの両方を表す訪問者を表します。この例では、1,069人の訪問者が1回のセッション中に[!DNL /pops/disclosure_pop.asp]と[!DNL /direct.asp/?ldPage=hme]の両方を見たことを示しています。
