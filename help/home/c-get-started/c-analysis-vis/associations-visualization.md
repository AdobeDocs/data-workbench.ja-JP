---
description: 関連付けテーブルのビジュアライゼーションでは、クラメールの V アルゴリズムを使用して、指標を指標、ディメンションおよびディメンションエレメントと関連付けることができます。
title: 関連付けテーブルのビジュアライゼーション
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 76%

---

# 関連付けテーブルのビジュアライゼーション{#association-table-visualization}

関連付けテーブルのビジュアライゼーションでは、クラメールの V アルゴリズムを使用して、指標を指標、ディメンションおよびディメンションエレメントと関連付けることができます。

関連付けテーブルは、[相関行列](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)および[クロス集計の弦](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html)のビジュアライゼーションで使用されるピアソン相関係数ではなく、クラメールの V 係数を使用して値を比較します（相関行列とクロス集計の弦で比較できるのは指標だけですが、関連付けテーブルと[関連付けの弦](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445)では指標、ディメンションおよびエレメントを比較できます）。

## 関連付けテーブルの作成 {#section-87ed12ccc1af4196a1b6534e621c4cbb}

関連付けテーブルは、可算ディメンションまたは非可算ディメンションに対して指標を比較します。テーブルを変更して、色の選択によってビジュアライゼーション内の関連付けをハイライトしたり、テキストマップ、ヒートマップまたはその両方として描画できます。

1. 関連付けテーブルを開きます。

   [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table]を右クリックします。

   ![](assets/association_table.png)

1. 拡張ディメンションである「クリックスルー」、「ヒット」、「製品」、「訪問」または「訪問者」ディメンションを選択します。拡張ディメンションが隅に表示され、関連指標が行と列の両方に配置された状態で関連付けテーブルが開きます。

   ![](assets/association_table1.png)

   関連付けテーブルは、クラメールの V を対称相関として使用するので、選択した指標、ディメンションおよびエレメントの値が関連付けテーブルの列と行の両方に反映されます。例えば、**Product**&#x200B;拡張ディメンションを選択すると、**[!UICONTROL Visits]**&#x200B;指標がテーブルの行と列の両方で関連指標として使用され、比較された値が同一なので、完全で役に立たない比較(1.00)が実行されます。

1. 関連付けテーブルにさらに値を追加します。

   列または行の中で右クリックして、「**指標を追加**」または「**ディメンションを追加**」を選択します。**ファインダー**&#x200B;パネルから指標およびディメンションをドラッグすることもできます。開いているテーブルからテーブルのビジュアライゼーションにディメンションエレメントをドラッグ＆ドロップすることもできます。

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >関連付けテーブルには、10行と10列までの制限があります。
