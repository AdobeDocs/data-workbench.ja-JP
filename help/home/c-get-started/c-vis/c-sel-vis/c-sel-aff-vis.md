---
description: ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。
title: 選択による他のビジュアライゼーションへの影響について
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 26%

---

# 選択による他のビジュアライゼーションへの影響について{#understanding-how-a-selection-affects-other-visualizations}

ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。

選択を行うと、Data Workbenchは、クエリの結果をフィルタリングし、ワークスペースでのビジュアライゼーションを生成します。 具体的なフィルターは、ビジュアライゼーションごとに異なります。

次の例は、Data Workbenchが3つの異なるタイプのビジュアライゼーションに選択を適用する方法を示しています。 これらの例を確認すると、ビジュアライゼーションに対する選択のフィルタリング効果がわかります。また、フィルタリングされたビジュアライゼーションに表示される結果の解釈方法についても説明します。

* [Sessions 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Visitors 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Sessions 指標でビジュアライゼーションをフィルタリングする {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=hme] URIによって、右側のビジュアライゼーションに表示されるセッションの指標がフィルタリングされています。

![](assets/client-vis1.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIに対してセッションをフィルタリングします。この例では、[!DNL /pops/disclosure_pop.asp]要素の値を生成するクエリを次のようにフィルタリングします。

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションとにリストされたURIを含むセッション数を表し [!DNL /direct.asp/?ldPage=hme]ます。この例では、訪問者が同じセッションで[!DNL /pops/disclosure_pop.asp]ページと[!DNL /direct.asp/?ldPage=hme]の両方を表示したセッションが1,113件あることを示しています。

## Visitors 指標でビジュアライゼーションをフィルタリングする {#section-97d38c7f03e8457189a9c72d69514ed2}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=home] URIによって、右側のビジュアライゼーションの訪問者数の指標がフィルタリングされています。

![](assets/client-vis2.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIに対して訪問者をフィルタリングします。この例では、[!DNL /pops/disclosure_pop.asp] URIの値を生成するクエリを次のようにフィルタリングします。

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションと（同じセッション中に限らないが）リストされたURIを表示した訪問者を表しま [!DNL /direct.asp/?ldPage=hme] す。上の例では、2,041人の訪問者が[!DNL /pops/disclosure_pop.asp]と[!DNL /direct.asp/?ldPage=hme]の両方を表示したことが示されています。

## Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする {#section-f746182311d648dcb98716b0fe846e25}

この例では、左側のビジュアライゼーションの[!DNL /direct.asp/?ldPage=hme] URIによって、右側のビジュアライゼーションのセッション別訪問者数の指標がフィルタリングされています。

![](assets/client-vis3.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択したURIに対して、セッション別に訪問者をフィルタリングします。例えば、[!DNL /pops/disclosure_pop.asp] URIの値を生成するクエリは次のようにフィルタリングされます。

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **ビジュアライゼーションの解釈：** フィルタリングされたビジュアライゼーションは、ビジュアライゼーションにリストされたURIと同じセッションの [!DNL /direct.asp/?ldPage=hme] 両方を表示した訪問者を表します。この例では、1,069人の訪問者が1回のセッション中に[!DNL /pops/disclosure_pop.asp]と[!DNL /direct.asp/?ldPage=hme]の両方を見たことが示されています。
