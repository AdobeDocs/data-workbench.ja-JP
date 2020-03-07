---
description: 関連付けテーブルのビジュアライゼーションでは、クラメールの V アルゴリズムを使用して、指標を指標、ディメンションおよびディメンションエレメントと関連付けることができます。
title: 関連付けテーブル 視覚化
uuid: 4563c336-3377-4929-8694-8c0d00866825
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 関連付けテーブルのビジュアライゼーション{#association-table-visualization}

関連付けテーブルのビジュアライゼーションでは、クラメールの V アルゴリズムを使用して、指標を指標、ディメンションおよびディメンションエレメントと関連付けることができます。

関連付けテーブルは、[相関行列](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)および[クロス集計の弦](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html)のビジュアライゼーションで使用されるピアソン相関係数ではなく、クラメールの V 係数を使用して値を比較します（相関行列とクロス集計の弦で比較できるのは指標だけですが、関連付けテーブルと[関連付けの弦](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445)では指標、ディメンションおよびエレメントを比較できます）。

## 関連付けテーブルの作成 {#section-87ed12ccc1af4196a1b6534e621c4cbb}

関連付けテーブルは、可算ディメンションまたは非可算ディメンションに対して指標を比較します。テーブルを変更して、色の選択によってビジュアライゼーション内の関連付けをハイライトしたり、テキストマップ、ヒートマップまたはその両方として描画できます。

1. 関連付けテーブルを開きます。

   Right-click [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table].

   ![](assets/association_table.png)

1. 拡張ディメンションである「クリックスルー」、「ヒット」、「製品」、「訪問」または「訪問者」ディメンションを選択します。拡張ディメンションが隅に表示され、関連指標が行と列の両方に配置された状態で関連付けテーブルが開きます。

   ![](assets/association_table1.png)

   関連付けテーブルは、クラメールの V を対称相関として使用するので、選択した指標、ディメンションおよびエレメントの値が関連付けテーブルの列と行の両方に反映されます。For example, selecting the **Product** extended dimension uses the **[!UICONTROL Visits]** metric as the associated metric in both the row and column of the table, resulting in a perfect yet useless comparison (1.00) because the compared values are identical.

1. 関連付けテーブルにさらに値を追加します。

   列または行の中で右クリックして、「**指標を追加**」または「**ディメンションを追加**」を選択します。**ファインダー**&#x200B;パネルから指標およびディメンションをドラッグすることもできます。開いているテーブルからテーブルのビジュアライゼーションにディメンションエレメントをドラッグ＆ドロップすることもできます。

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >関連付けテーブルには、10行および10列までの制限があります。

