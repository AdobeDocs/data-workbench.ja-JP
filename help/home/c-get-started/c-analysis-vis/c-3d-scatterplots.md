---
description: 3D 散布グラフは、x、y、z 軸が様々な指標を表す 3 次元のグリッド上にデータディメンションのエレメント（日や参照サイトなど）をグラフ化します。
solution: Analytics
title: 3D 散布グラフ
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 3D 散布グラフ{#d-scatter-plots}

3D 散布グラフは、x、y、z 軸が様々な指標を表す 3 次元のグリッド上にデータディメンションのエレメント（日や参照サイトなど）をグラフ化します。

[2D 散布グラフ](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots)と同様に、このビジュアライゼーションは、様々な指標を使用して、異なる多数のアイテムの関係を把握する場合に役立ちます。

**3D 散布グラフビジュアライゼーションを利用するには：**

1. 新しいワークスペースを開きます。

   新しいワークスペースを開いた後に、**追加**／**一時的にロック解除**&#x200B;をクリックする必要がある場合があります。
1. 右クリックし、**ビジュアライゼーション**／**3D 散布グラフ**&#x200B;を選択します。

   A menu listing **[!UICONTROL Dimensions]** will open.

1. クエリーのディメンションを選択します。

   3D 散布グラフが開き、そのディメンションのデフォルトの指標が表示されます。

   ![](assets/3D_main.png)

   メニューを選 **[!UICONTROL Days]** 択すると、以下の3D散布グラフが表示され、以下の軸にこれらのデフォルトの指標が表示されます。 **[!UICONTROL x=Visits]**、、 **[!UICONTROL y=Retention]**&#x200B;および **[!UICONTROL z=Visits]**。

1. 指標を変更します。Right-click on the metric label in the x, y, or z axis and select **[!UICONTROL Change Metric]**. 次に、選択した軸の別の指標を選択します。

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * 指標をドラッグして、3 つの軸ラベルの 1 つにドロップすると、選択した軸がドロップした指標に変更されます。
   >    * 指標をドラッグして、ビジュアライゼーションの任意の場所にドロップすると、その軸の半径指標が変更されます。
   >    * ディメンションをドラッグして、ビジュアライゼーションの任意の場所にドロップすると、そのビジュアライゼーションのディメンションが変更されます。


1. 半径指標を変更します。Right-click the title at the top of the page (titled after the selected dimension) and select **[!UICONTROL Change Radius Metric]**.

   半径指標は、指標の選択に基づいてプロットされた点のサイズを定義します。散布グラフ内の点の相対位置は変更されませんが、ビジュアライゼーション内のプロットされた点のサイズが指標値に応じて大きくなります。

   ![](assets/3D_change_radius.png)

1. を使用しま **[!UICONTROL Orthographic Camera]**&#x200B;す。 このオプションを使用すると、半径指標に基づいた実際のサイズでプロットされた点を表示して、3 次元の歪みを回避することができます。

   3D 散布グラフは、最初に表示されたときは、3 次元の回転投影図で表示されます。そのため、視点（仮想的な「カメラ」）の近くにプロットされた点には歪みが生じます（カメラの近くにプロットされた点は、カメラから離れて回転する点よりもはるかに大きく表示されます）。

   To avoid this perspective distortion, you can select the **[!UICONTROL Orthographic Camera]** option by right-clicking on the title and selecting from the menu. すると、3 次元の物体を 2 次元で表示することができます。その場合は、プロットされた点が平らにレンダリングされ、半径指標を基準に点が表示されるので、3 次元の補正が弱まります。

1. 散布グラフから点を選択します。

   * **点または点のグループを削除するには**：点をクリックします。
   * **選択範囲に別の点または点のグループを追加するには**：**Ctrl** キーを押しながら点を&#x200B;**クリック**&#x200B;するか、**Ctrl** キーを押しながら複数の点を&#x200B;**ドラッグ**&#x200B;します。

   * **選択範囲から点または点のグループを削除するには**：**Shift** キーを押しながら点を&#x200B;**クリック**&#x200B;するか、**Shift****** キーを押しながら複数の点を&#x200B;**ドラッグ**&#x200B;します。

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

