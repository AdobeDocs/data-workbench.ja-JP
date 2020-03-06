---
description: 階層ビューは、Site または HBX アプリケーションを使用している場合にのみ表示可能です。
solution: Analytics
title: 階層ビューの適用
topic: Data workbench
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 階層ビューの適用{#apply-hierarchy-views}

階層ビューは、Site または HBX アプリケーションを使用している場合にのみ表示可能です。

階層ビューでは、Web サイト内のページがファイル名で階層的にまとめられ、アルファベット順に並べ替えられて表示されます。階層ビューは分析に役立ちますが、プロセスマップなどの高度なビジュアライゼーションの設定にも使用できます。プロセスマップについて詳しくは、「 [プロセスマップ](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>データセットがクラスター内の複数のサーバーで実行するように設定されている場合、この機能を正しく動作させるには、システム管理者が中央標準化サーバーとして機能するマシンを指定する必要があります。 指定する手順については、『*データセット設定ガイド*』の「ログ処理設定ファイル」の章を参照してください。

![](assets/vis_Table_CompareHierarchy.png)

**階層ビューを有効または無効にするには**

* From any page or URI visualization, right-click an element or the label of the page dimension and click **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   An X is shown next to the option when the [!DNL hierarchy view] is active.

   階層は、ツリー構造を使用して Web サイトのセクションとページにまとめられます。セクション（ノード）は、セクション名の横の+記号または — 記号を使用して展開したり、折りたたんだりできます。 個々のページの横には+記号や — 記号は表示されません。

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## 階層ビューでのディメンション要素のマスク {#section-e477c469934846da8d807f92fc2f3ed1}

マスクとは、データのサブセットまたはディメンション内の要素のサブセットを選択することです。分析に含めたくない要素をマスクまたは非表示にします。Using the [!DNL Mask] menu options for hierarchy views, you select the minimum percentage of a metric that an element must have to be displayed in the visualization.

**メニューオプションを使用してデータをマス[!DNL Mask]クするには**

1. Right-click an element or the label of the dimension and click **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. 「次の値より大きい」で適切な割合をクリックしてから、マスクする指標をクリックします。

例えば、0.1 ％をクリックしてから Page Views をクリックした場合、ページビューの総数の 0.1 ％以下の要素はマスクされ（非表示）、ページビューの総数の 0.1 ％を上回る要素が表示されます。0 ％をクリックした場合は、選択した指標に対して 0（ゼロ）の値を持つすべての要素がマスクされます。
