---
description: 3D 散布グラフは、x、y、z 軸が様々な指標を表す 3 次元のグリッド上にデータディメンションのエレメント（日や参照サイトなど）をグラフ化します。
title: 3D 散布グラフ
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 83%

---

# 3D 散布グラフ{#d-scatter-plots}

3D 散布グラフは、x、y、z 軸が様々な指標を表す 3 次元のグリッド上にデータディメンションのエレメント（日や参照サイトなど）をグラフ化します。

[2D 散布グラフ](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots)と同様に、このビジュアライゼーションは、様々な指標を使用して、異なる多数のアイテムの関係を把握する場合に役立ちます。

**3D 散布グラフビジュアライゼーションを利用するには：**

1. 新しいワークスペースを開きます。

   新しいワークスペースを開いた後に、**追加**／**一時的にロック解除**&#x200B;をクリックする必要がある場合があります。
1. 右クリックし、**ビジュアライゼーション**／**3D 散布グラフ**&#x200B;を選択します。

   **[!UICONTROL Dimensions]**&#x200B;をリストするメニューが開きます。

1. クエリーのディメンションを選択します。

   3D 散布グラフが開き、そのディメンションのデフォルトの指標が表示されます。

   ![](assets/3D_main.png)

   **[!UICONTROL Days]**&#x200B;メニューを選択すると、次の3D散布グラフが表示され、以下の軸にこれらのデフォルトの指標が表示されます。**[!UICONTROL x=Visits]**、**[!UICONTROL y=Retention]**、および&#x200B;**[!UICONTROL z=Visits]**。

1. 指標を変更します。x、yまたはz軸の指標ラベルを右クリックし、「**[!UICONTROL Change Metric]**」を選択します。 次に、選択した軸の別の指標を選択します。

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * 指標をドラッグして、3 つの軸ラベルの 1 つにドロップすると、選択した軸がドロップした指標に変更されます。
   >    * 指標をドラッグして、ビジュアライゼーションの任意の場所にドロップすると、その軸の半径指標が変更されます。
   >    * ディメンションをドラッグして、ビジュアライゼーションの任意の場所にドロップすると、そのビジュアライゼーションのディメンションが変更されます。


1. 半径指標を変更します。ページ上部のタイトル（選択したディメンションの後のタイトル）を右クリックし、「**[!UICONTROL Change Radius Metric]**」を選択します。

   半径指標は、指標の選択に基づいてプロットされた点のサイズを定義します。散布グラフ内の点の相対位置は変更されませんが、ビジュアライゼーション内のプロットされた点のサイズが指標値に応じて大きくなります。

   ![](assets/3D_change_radius.png)

1. **[!UICONTROL Orthographic Camera]**&#x200B;を使用します。 このオプションを使用すると、半径指標に基づいた実際のサイズでプロットされた点を表示して、3 次元の歪みを回避することができます。

   3D 散布グラフは、最初に表示されたときは、3 次元の回転投影図で表示されます。そのため、視点（仮想的な「カメラ」）の近くにプロットされた点には歪みが生じます（カメラの近くにプロットされた点は、カメラから離れて回転する点よりもはるかに大きく表示されます）。

   この遠近法の歪みを回避するには、タイトルを右クリックし、メニューから「 **[!UICONTROL Orthographic Camera]** 」オプションを選択します。 すると、3 次元の物体を 2 次元で表示することができます。その場合は、プロットされた点が平らにレンダリングされ、半径指標を基準に点が表示されるので、3 次元の補正が弱まります。

1. 散布グラフから点を選択します。

   * **点または点のグループを削除するには**：点をクリックします。
   * **選択範囲に別の点または点のグループを追加するには**：**Ctrl** キーを押しながら点を&#x200B;**クリック**&#x200B;するか、**Ctrl** キーを押しながら複数の点を&#x200B;**ドラッグ**&#x200B;します。

   * **選択範囲から点または点のグループを削除するには**：**Shift** キーを押しながら点を&#x200B;**クリック**&#x200B;するか、**Shift****** キーを押しながら複数の点を&#x200B;**ドラッグ**&#x200B;します。

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
