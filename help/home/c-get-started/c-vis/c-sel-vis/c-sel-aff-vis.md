---
description: ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。
title: 選択による他のビジュアライゼーションへの影響について
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 26%

---

# 選択による他のビジュアライゼーションへの影響について{#understanding-how-a-selection-affects-other-visualizations}

{{eol}}

ワークスペース内で、ビジュアライゼーションにはクエリー結果のセットが表示されます。

選択を行うと、Data Workbenchは、ワークスペースでビジュアライゼーションを生成するために使用するクエリの結果をフィルタリングします。 具体的なフィルターは、ビジュアライゼーションごとに異なります。

次の例は、Data Workbenchが 3 つの異なるタイプのビジュアライゼーションに選択を適用する方法を示しています。 これらの例を確認すると、ビジュアライゼーションに対する選択のフィルタリング効果がわかります。また、フィルタリングされたビジュアライゼーションに表示される結果の解釈方法についても説明します。

* [Sessions 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [Visitors 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## Sessions 指標でビジュアライゼーションをフィルタリングする {#section-7cc06493ecb34cd4a696dbf0f0a7aaef}

この例では、 [!DNL /direct.asp/?ldPage=hme] 左側のビジュアライゼーションの URI は、右側のビジュアライゼーションに表示されるセッションの指標をフィルタリングしています。

![](assets/client-vis1.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択した URI に対して Sessions をフィルタリングします。 この例では、 [!DNL /pops/disclosure_pop.asp] 要素は、次のようにフィルタリングされます。

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **ビジュアライゼーションの解釈：** フィルター適用済みのビジュアライゼーションは、ビジュアライゼーションにリストされた URI を含むセッション数と [!DNL /direct.asp/?ldPage=hme]. この例では、訪問者が両方を閲覧したセッションが 1,113 件あったことを示しています [!DNL /pops/disclosure_pop.asp] ページと [!DNL /direct.asp/?ldPage=hme] 同じセッションで

## Visitors 指標でビジュアライゼーションをフィルタリングする {#section-97d38c7f03e8457189a9c72d69514ed2}

この例では、 [!DNL /direct.asp/?ldPage=home] 左側のビジュアライゼーションの URI により、右側のビジュアライゼーションの訪問者数の指標がフィルタリングされています。

![](assets/client-vis2.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択した URI に対して訪問者をフィルターします。 この例では、 [!DNL /pops/disclosure_pop.asp] URI は次のようにフィルタリングされます。

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **ビジュアライゼーションの解釈：** フィルター適用済みのビジュアライゼーションは、ビジュアライゼーションにリストされた URI を表示した訪問者と [!DNL /direct.asp/?ldPage=hme] （ただし、同じセッション中に限るわけではありません）。 上記の例では、2,041 人の訪問者が両方を閲覧したことを示しています [!DNL /pops/disclosure_pop.asp] および [!DNL /direct.asp/?ldPage=hme].

## Visitors-by-Session 指標でビジュアライゼーションをフィルタリングする {#section-f746182311d648dcb98716b0fe846e25}

この例では、 [!DNL /direct.asp/?ldPage=hme] 左側のビジュアライゼーションの URI により、右側のビジュアライゼーションのセッション別訪問者数の指標がフィルタリングされています。

![](assets/client-vis3.png)

* **クエリに対する選択の効果：** Data Workbenchは、選択した URI に対して、訪問者をセッション別にフィルターします。 例えば、 [!DNL /pops/disclosure_pop.asp] URI は次のようにフィルタリングされます。

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **ビジュアライゼーションの解釈：** フィルター適用済みビジュアライゼーションは、ビジュアライゼーションにリストされた URI と [!DNL /direct.asp/?ldPage=hme] 同じセッション中に この例では、1,069 人の訪問者が [!DNL /pops/disclosure_pop.asp] および [!DNL /direct.asp/?ldPage=hme] 1 回のセッション中に
