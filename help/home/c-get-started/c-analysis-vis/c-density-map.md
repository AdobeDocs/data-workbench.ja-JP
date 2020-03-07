---
description: 密度マップビジュアライゼーションは、四角形のマップ内にエレメントを影付きの長方形として表示します。
solution: Analytics
title: 密度マップ
topic: Data workbench
uuid: c13cecee-f322-4757-aa90-12039173ff9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 密度マップ{#density-map}

密度マップビジュアライゼーションは、四角形のマップ内にエレメントを影付きの長方形として表示します。

長方形のサイズはエレメントの値によって異なります。値が大きいほど、大きい面積の長方形で表されます。円グラフと同様に、このビジュアライゼーションを使用すると、選択したディメンションの中で最も大きな割合を占めているエレメントをすぐに確認することができます。

![](assets/density_map_day_visits.png)

密度マップを作成するには：

1. 新しいワークスペースを開きます。

   新しいワークスペースを開いた後に、**追加**／**一時的にロック解除**&#x200B;をクリックする必要がある場合があります。
1. クリック **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. Select a **[!UICONTROL Dimension]** from the menu.

   For example, select **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   In contrast, selecting **[!UICONTROL Time]** > **[!UICONTROL Hours]** would give you more elements with smaller values displaying as smaller rectangles.

   >[!NOTE]
   >
   >必要に応じて複数の要素を持つディメンションを選択します。 現在、ディメンションごとのエレメント数は最大 200 個に制限されています。

1. You can change dimension views by opening **[!UICONTROL Visualization]** > **[!UICONTROL Table]** and selecting across elements from the table to display in the map.

   ![](assets/density_map_day_selections.png)

   マップは、テーブルからの選択に応じて変更されます。

1. 小さなエレメントの上にカーソルを置くと、マウスカーソルの近くに表示されるテキスト内にそのエレメントの名前と値が表示されます。
1. Mask elements by right-clicking and selecting **[!UICONTROL Mask]**, then choose an option.

   ![](assets/density_map_day_mask.png)

   To display all masked nodes, select **[!UICONTROL Unhide All]**.

1. Spotlight elements by right-clicking and selecting **[!UICONTROL Spotlight]**, then choose an option. スポットライトを使用すると、範囲内のエレメントに明暗を付けることができます。
1. ワークスペースに色凡例を追加します。色凡例を使用して、マップ内の値を識別することができます。

   ワークスペースに色凡例を追加できます。ノードの色は、データの追加のディメンションに基づいて変更されます。
1. マップのタイトルを右クリックし、メニューから選択して、ディメンションまたは指標を変更します。

   ![](assets/density_map_change_dim.png)

1. Add callouts by right-clicking a cell and selecting **[!UICONTROL Add Callout]**. メニューから様々なタイプやビジュアライゼーションを選択できます。

   ![](assets/density_map_callout.png)

1. すべてのビジュアライゼーション内で同様に、タイトルバーの上を右クリックして、「閉じる」、「保存」、「Excel にエクスポート」、「注文」、「コピー」、「最小化」および枠のないビジュアライゼーションを表示する「枠なし」という基本コマンドを使用できます。

   ![](assets/density_map_export.png)

1. 密度マップでは、他のビジュアライゼーションと同様に、複数のエレメントを選択および選択解除できます。

* エレメントを選択するには、左クリックします。
* 複数のエレメントを選択するには、Ctrl キーを押しながらクリックします。
* エレメントを選択解除するには、Shift キーを押しながらクリックします。
* メニューを開くには、選択したエレメント内で右クリックします。次に、またはを **[!UICONTROL Deselect]** 選択して、 **[!UICONTROL Deselect All]** 選択した要素を消去します。

## 追加のオプション {#section-d77defb012424de4a7ced8e5c93115bc}

密度マップを右クリックすると、メニューが開き、次のオプションが表示されます。

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> オプション </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 追加 引き出し線 </td> 
   <td colname="col2">エレメントをさらに識別または説明するために、ビジュアライゼーションに引き出し線としてテキストやグラフィックを追加します。 <p>また、密度マップで選択されているエレメントに基づいて、空の指標の凡例、テーブル、折れ線グラフまたは散布グラフを選択することもできます。その後、必要に応じて、これらの空のビジュアライゼーションに指標やディメンションを追加できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マスク </td> 
   <td colname="col2">マスクオプションを使用すると、選択したエレメントを非表示にできます。右クリックすると、マスクオプションが表示されます。 <p><span class="uicontrol">この要素を非表示</span>：選択した 1 つのエレメントをマスクする場合は、このオプションを選択します。 </p> <p><span class="uicontrol">選択項目を非表示</span>：選択した複数のエレメントをマスクする場合は、このオプションを選択します。 </p> <p><span class="uicontrol">上位を表示</span>：密度マップで値に基づいて上位 100、50、25 または 10 個のエレメントのみを表示する場合は、このオプションを選択します。 </p> <p><span class="uicontrol">下位を表示</span>：密度マップで値に基づいて下位 100、50、25 または 10 個のエレメントのみを表示する場合は、このオプションを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> スポットライト </td> 
   <td colname="col2"> スポットライトを使用すると、範囲内のエレメントに明暗を付けることができます。右クリックすると、メニューが開き、次のオプションが表示されます。 <p><span class="uicontrol">上位を表示</span>：密度マップで値に基づいて上位 100、50、25 または 10 個のエレメントのみを強調表示する場合は、このオプションを選択します。 </p> <p><span class="uicontrol">下位を表示</span>：密度マップで値に基づいて下位 100、50、25 または 10 個のエレメントのみを強調表示する場合は、このオプションを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>選択を解除 </p> <p>すべて選択解除 </p> </td> 
   <td colname="col2"> <p> 現在のエレメント（選択されている場合）を解除する場合、または選択されているすべてのエレメントを選択解除する場合は、これらのコマンドを選択します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
