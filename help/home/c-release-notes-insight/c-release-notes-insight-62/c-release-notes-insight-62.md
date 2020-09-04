---
description: Data Workbench 6.2 のリリースノートには、新機能、アップグレード要件、バグの修正および既知の問題が含まれています。
title: Data Workbench 6.2 のリリースノート
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 83%

---


# Data Workbench 6.2 のリリースノート{#data-workbench-release-notes}

Data Workbench 6.2 のリリースノートには、新機能、アップグレード要件、バグの修正および既知の問題が含まれています。

## 新機能 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2 には、次の新機能が含まれています。

| 機能 | 説明 |
|--- |--- |
| デシジョンツリー | デシジョンツリーは予測分析のビジュアライゼーションで、訪問者の特性と関係を評価するために使用されます。デシジョンツリービルダーは、指定されたポジティブケースと一連の入力に基づいて、デシジョンツリービジュアライゼーションを生成します。 |
| 相関行列のバイナリフィルターの更新 | バイナリフィルターは更新され、新機能が追加されました。そのため、以前のバージョンで作成したバイナリフィルターを使用した相関行列はすべて作成し直す必要があります。 |
| 密度マップ | 密度マップは、四角形のマップ内にエレメントを影付きの長方形として表示するビジュアライゼーションです。 |
| アトリビューションプロファイル | アトリビューション値（コンバージョンや販売の成功に寄与しているイベント）をすばやく分析するために、Data Workbench には、ルールに基づくアトリビューションプロファイルと、アーキテクトがアトリビューションレポートを設定し、アナリストがレポートを実行するための機能が用意されています。 |
| 分析レポート | レポートテンプレートは、Adobe SC プロファイルを利用する Data Workbench ユーザーのために、Adobe Analytics のレポートを標準化します。これらのレポートは、Marketing Reports および Analytics（旧 SiteCatalyst）で利用されているレポートと同じです。 |
| 3D 散布グラフ | 3D 散布グラフは、x、y、z 軸が様々な指標を表す 3 次元のグリッド上にデータディメンションのエレメント（日や参照サイトなど）をグラフ化します。 |


## Data Workbench クライアントの UI の更新{#data-workbench-client-ui-updates}

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

新しいクイックキーを使用すると、ウィンドウビューと全ページビューを切り替えてワークスペースをサイズ変更して再適合できます。

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

## バグの修正 {#section-8704a9ac358246cd81233dd0982d534f}

* 検索エンジンによるクエリー検索語の変更に対処するようにビジュアルサイトルックアップファイルが更新されました。
* クライアントワークステーションでワークスペースをインポートすると、インポートが成功した場合でも、「ワークスペースをインポートできません」という不正確なエラーメッセージが表示される問題を修正しました。
* ワークステーションの接続エラー発生時に表示される「412 構成の競合」というメッセージが、システム動作を示すユーザーにわかりやすいメッセージに置き換えられました。
* レポートサーバーで「投稿」コマンドが実行できるようになりました。
* 簡体字中国語用のクライアントユーザーインターフェイスのエラーを修正しました。
* Adobe Analyticsは、Data Workbenchを強化するデータフィードを更新し、Adobe Experience Cloudと統合されるプロファイルとオーディエンスを活用しました。 2014 年 4 月 21 日までに、Data Workbench のすべてのユーザーはこの移行のために環境の準備を行う必要がありました。

   Adobe Analytics全土の顧客を完全に表示するプロファイルやオーディエンスが導入されました。 この新しいサービスは、分析ツールの価値をさらに高め、Analytics内でこれらの機能の基盤を構築する開始を実現するために、Adobe Experience Cloud内で利用できます。 新しいExperience Cloud訪問者IDがデータフィードに追加され、新しいデータフィードおよびグローバル訪問者IDに対応するためのその他の機能強化や改善が行われます。
* ワークスペースをインポートすると、インポートが成功した場合でも、エラーメッセージが表示されます。

## アップグレード要件 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* アトリビューションプロファイルは、Analytics（SC／Insight）のデータフィードを利用する Adobe SC プロファイルを実装しているユーザー用に設定されています。デフォルトでは、ルールに基づくモデルで評価されたデフォルトのインタラクションとしてマーケティングイベントとコンバージョンイベントが使用されます。
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. これは、設定ファイルをデフォルトの設定から変更している場合にのみ問題となります。

* If you have deleted unused fields in the **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile.

## 既知の問題 {#section-dbb307639835493a83409f5f461932b8}

* 3D 散布グラフビジュアライゼーションに引き出し線が含まれている場合に、ズームを使用すると、ビジュアライゼーションの境界線の外にプロットが表示されることがあります。

   回避策：最初に 3D 散布グラフをズームしてから、ビジュアライゼーションに引き出し線を追加します。
* ファインダーパネルから指標列の外にある指標の凡例に指標をドラッグすると、ワークスペースから指標の凡例が削除されます。

   回避策：指標の凡例に指標をドラッグする場合は、最初の列（指標列）にドロップする必要があります。
* 「サイドバー」と「両方」オプションを使用しているワークスペースを印刷すると、印刷されたページに著作権情報が含まれません。
* リモートデスクトップセッションでワークステーションを使用しているときに、ワークスペースの名前を変更すると、クラッシュします。
* （簡体字中国語版の場合）Report Server では実際のレポート出力が有効ですが、電子メールの件名や添付ファイル名が文字化けします。
* （簡体字中国語版の場合）ワークシートのビジュアライゼーションで折り返しを使用しても、ローカライズされた語句が正しく折り返されず、文字列に余計な文字が追加されます。
* （簡体字中国語版の場合）インストールディレクトリの名前に英語以外の文字が含まれている場合に、Insight.exe を起動することができません。

   回避策：デフォルトの名前のままにするか、フォルダーパスに英文字のみを使用して名前を変更して、実行可能ファイルを起動します。

