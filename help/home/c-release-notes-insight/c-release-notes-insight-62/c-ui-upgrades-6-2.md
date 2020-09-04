---
description: Data Workbench 6.2 には、新しいユーザーインターフェイス（ブックマークパネル、ワークスペースツールバーの新しいアイコン、画面内でワークスペースをドラッグする機能、新しいクイックキー）および円グラフビジュアライゼーションが追加されました。
title: Data Workbench クライアントの UI の更新
uuid: 1bc18c90-8b46-4c90-b7a7-2c6710e1e28c
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 92%

---


# Data Workbench クライアントの UI の更新{#data-workbench-client-ui-updates}

Data Workbench 6.2 には、新しいユーザーインターフェイス（ブックマークパネル、ワークスペースツールバーの新しいアイコン、画面内でワークスペースをドラッグする機能、新しいクイックキー）および円グラフビジュアライゼーションが追加されました。

## 新しいブックマーク機能 {#section-e361b605441540ca8213c3fddb5e0718}

重要なワークスペースにブックマークを追加して、ワークフローで使用しているビジュアライゼーションやレポート間をすばやく移動できるようになりました。

**ブックマークの使用**

1. ワークスペースにブックマークを追加するには、ツールバーの右上隅にあるブックマークアイコン ![](assets/bookmark_icon.png) をクリックします。
1. 左側のペインで&#x200B;**[!UICONTROL 追加]**／**[!UICONTROL ブックマークパネル]**&#x200B;をクリックして、ブックマークのリストを開きます。

   ![](assets/bookmarks_panel.png)

1. ブックマーク付きのワークスペースを開くには、**[!UICONTROL ブックマークパネル]**&#x200B;でワークスペース名をクリックします。

   ![](assets/bookmarks_panel_left.png)

   選択したワークスペースが開きます。ブックマーク付きの別のワークスペースをクリックすると、前のワークスペースが閉じ、新しく選択したワークスペースが開き、ワークフロー内をすばやく移動できます。

**ブックマークを削除するには：**

* In the Bookmark Panel, right-click and select **Remove`<bookmark title>`** to delete a selected bookmark, or select **[!UICONTROL Clear All Bookmarks]** to delete all bookmarks.

* ワークトップ内のサムネールビューでワークスペースを右クリックして、「**[!UICONTROL ブックマークをクリア]**」を選択することもできます。

>[!IMPORTANT]
>
>* ブックマークは、25 個まで保存できます。
>* ブックマークを追加した後に、ワークスペースの場所を移動すると、ブックマークが無効になるため、ブックマークパネルから削除してリセットする必要があります。

>



## ワークスペースの新しいアイコン {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 では、ワークスペース内のテキストがアイコンに置き換えられました。ただし、カーソルを上に置くと、**[!UICONTROL ファイル]**、**[!UICONTROL 追加]**、**[!UICONTROL エクスポート]**&#x200B;など、アイコンの機能を示すツールチップメッセージが表示されます。

![](assets/new_icons.png)

以下のリンクを含む、ドキュメントやその他のナレッジセンターにアクセスできる新しい&#x200B;**[!UICONTROL ヘルプ]**&#x200B;アイコンが追加されました。

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ドキュメントのリンク </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Marketing Reports &amp; Analytics </td> 
   <td colname="col2"><span class="uicontrol">Adobe Marketing Reports &amp; Analytics</span> のヘルプページが開きます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アイデア交換 </td> 
   <td colname="col2"><span class="uicontrol">Idea Exchange のログイン</span>が開きます。このオンラインポータルでは、ユーザーが Data Workbench への更新の変更や機能拡張のアイデアを投稿することができます。これらの顧客中心のアイデアに対して後ですべてのユーザーによる投票が行われます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ヘルプ </td> 
   <td colname="col2"><span class="uicontrol">Data Workbench のドキュメント</span>を開きます。 <p><span class="uicontrol">F1</span> キーを押して、ワークスペース内でヘルプを開くこともできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> バージョン情報 </td> 
   <td colname="col2">Data Workbench の<span class="uicontrol">クライアントバージョン</span>が表示されます。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>You can also press `<F1>` to open the documentation from a workspace.

## ワークスペースビューのドラッグ {#section-9129c340c21d45a3864c923884cd4382}

ワークスペースが表示可能な画面よりも大きい場合は、ビューを移動して、ワークスペース内のすべてのエレメントを表示できます。背景（ビジュアライゼーションとテーブルの外側）をクリックし、画面をドラッグすると、ワークスペース内で表示可能な領域を移動できます。ワークスペースの枠内でビューをドラッグしているときは、カーソルが手のアイコンに変わります。

![](assets/drag_workspace.png)

## ワークスペースビューを変更するクイックキー {#section-d8322f72423f437aa2e34f2188b1341c}

新しいクイックキーを使用すると、ウィンドウビューと全ページビューを切り替えてワークスペースをサイズ変更して再適合できます。キーボードクイックキーについて詳しくは、[クイックリファレンス](https://docs.adobe.com/content/help/en/data-workbench/using/client/visualizations/c-qk-ref.html)を参照してください。

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> コマンド </th> 
   <th colname="col2" class="entry"> クイックキー </th> 
   <th colname="col3" class="entry"> 組み合わせられるメニューコマンド </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>フルスクリーンビュー</b>。ワークスペースが画面を埋め、新しいサイズに再適合されます。 </td> 
   <td colname="col2"><b>Ctrl プラス（+）</b> <p>Ctrl + +（キーパッド） </p> <p><i>または</i> </p> <p>Ctrl + Shift + +（キーボード） </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">ファイル／ページサイズ／画面にフィット <p><i>を選択し、次に以下を選択</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">ファイル／ワークスペースを再適合 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>ウィンドウビュー</b>。ワークスペースが標準のウィンドウビューで表示され、新しいサイズに再適合されます。 </td> 
   <td colname="col2"><b>Ctrl マイナス（-）</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">ファイル／ページサイズ／標準 <p><i>を選択し、次に以下を選択</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">ファイル／ワークスペースを再適合 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

