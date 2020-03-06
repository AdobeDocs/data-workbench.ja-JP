---
description: 棒グラフ、テーブル、階層ビューから空白のマップに要素をドラッグアンドドロップすることにより、2D プロセスマップや 3D プロセスマップを作成できます。
solution: Analytics
title: プロセスマップの作成
topic: Data workbench
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Create a process map{#create-a-process-map}

棒グラフ、テーブル、階層ビューから空白のマップに要素をドラッグアンドドロップすることにより、2D プロセスマップや 3D プロセスマップを作成できます。

追加できる要素は、プロセスマップのベースディメンションの要素でなければなりません。同じベースディメンションを使用していれば、1 つのプロセスマップから別のプロセスマップにノードをドラッグアンドドロップすることもできます。さらに、マップ全体をズームまたは移動して特定のノードにフォーカスしたり、他のビジュアライゼーションタイプに変更したりできます。「[ビジュアライゼーションへのズーム](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530)」を参照してください。

**テーブルまたは棒グラフを使用してプロセスマップに要素を追加するには**

* プロセスマップと同じベースディメンションを持つ任意のテーブルまたは棒グラフから、Ctrl + Alt キーを押しながら個々の要素をクリックして、プロセスマップにドラッグします。マウスがプロセスマップに達するまで、マウスカーソルには「No」という語が表示されます。

   >[!NOTE]
   >
   >追加できる要素は、プロセスマップのベースディメンションの要素でなければなりません。

   ![](assets/vis_2DProcessMap_addPages.png)

**階層ビューを使用してプロセスマップに要素を追加するには**

>[!NOTE]
>
>分析する階層の最上位レベルのノードを追加することをお勧めします。

1. From any table or bar graph with the same base dimension as the process map, right-click an element or the label of the base dimension and click **[!UICONTROL Hierarchy View]**.
1. Ctrl + Alt キーを押しながら、要素をクリックしてプロセスマップにドラッグします。マウスがプロセスマップに達するまで、マウスカーソルには「No」という語が表示されます。

   >[!NOTE]
   >
   >追加できる要素は、プロセスマップのベースディメンションの要素でなければなりません。

   1 つの要素をプロセスマップにドラッグすると、その要素のみに対して 1 つのマップノードが作成されますが、複数の要素（グループ）または複数の要素を含むフォルダーを選択して階層からドラッグすると、そのグループまたはフォルダーに対して 1 つのノードが作成されます。For example, if you are working with website data, dragging a folder named [!DNL site.com/cgi-bin] onto a map makes a node called [!DNL site.com/cgi-bin/*], which represents all pages and directories that are children of that folder.

ページ階層ビューの詳細は、「階層ビューの適用」を [参照してください](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff)。

**別のプロセスマップからノードをプロセスマップに追加するには**

>[!NOTE]
>
>プロセスマップには、同じベースディメンションが必要です。

* 以下の方法を使用して、最初のプロセスマップから 2 つ目のプロセスマップにノードをコピーします。

   * 個々のノードをコピーするには、ノードごとにクリックし、2 つ目のプロセスマップにドラッグします。
   * 複数のノードをコピーするには、Ctrl キーを押しながらクリックしてドラッグし、コピーするノードの周囲にボックスを作成します。次に、ボックスをクリックして、ハイライトされているノードを 2 つ目のプロセスマップにドラッグします。ハイライトされているノードがすべて 2 つ目のプロセスマップにコピーされます。

