---
description: 依存関係マップにデータセットコンポーネントを表示する場合、「ファイルブロックを含める」表示オプションを有効にできます。
solution: Analytics
title: ファイルブロック
topic: Data workbench
uuid: 079dccba-ef19-4895-90bb-6c56f26e8beb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ファイルブロック{#file-blocks}

依存関係マップにデータセットコンポーネントを表示する場合、「ファイルブロックを含める」表示オプションを有効にできます。

このオプションを有効にすると、マップには、1 つのデータセット設定ファイルに定義された変換すべてに対して青のノードが 1 つ表示され、1 つのデータセット設定ファイルに定義された拡張ディメンションすべてに対して緑のノードが 1 つ表示されます。For example, if a [!DNL log processing dataset include] file includes the definitions of three transformations, the map displays one blue node representing the three transformations. Similarly, if a [!DNL transformation dataset include] file includes the definitions of two extended dimensions, the map displays one green node representing the two extended dimensions.

## Transformation blocks {#section-c442730394264a0b850792a32eaaa2da}

青のノードはそれぞれ変換ブロックであり、次のオプションがあります。

* To view the input fields of the transformation block, right-click the node for the block and click **[!UICONTROL Inputs]**.
* To view the output fields of the transformation block, right-click the node for the block and click **[!UICONTROL Outputs]**.
* To edit any of the transformations in the block, right-click the node for the block and click **[!UICONTROL Edit Configuration]**. 表示される引き出し線には設定ファイル全体が含まれ、ここにすべての変換が定義されています。ここで必要に応じてパラメーターを編集できます。これらのパラメーターについて詳しくは、『*データセット設定ガイド*』を参照してください。

* To see all of the transformations in the block, right-click the node for the transformation block and click **[!UICONTROL Show Details]**. 表示される引き出し線には、別の依存関係マップが含まれ、ブロック内のすべての変換に対するノードが表示されます。

## Dimension blocks {#section-0dd581ac6dfc4153bee5300b3cfae2a0}

緑のノードはそれぞれディメンションブロックであり、次のオプションがあります。

* To view the input fields or the parent dimension of the dimension block, right-click the node for the block and click **[!UICONTROL Inputs]**.
* To view the output dimensions of the dimension block, right-click the node for the block and click **[!UICONTROL Outputs]**.

