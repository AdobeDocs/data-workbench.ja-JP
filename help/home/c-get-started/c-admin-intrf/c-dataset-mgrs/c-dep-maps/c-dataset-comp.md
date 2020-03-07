---
description: データセットコンポーネントに関する概念情報です。
solution: Analytics
title: データセットコンポーネント
topic: Data workbench
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dataset components{#dataset-components}

データセットコンポーネントに関する概念情報です。

下の図に、ノードがデータセットのログソース、フィールド、変換、拡張ディメンションを表している依存関係マップを示します。

![](assets/vis_DependencyMap.png)

* 黄緑のノードは、データセット内で定義されている 1 つ以上のログソースまたはフィルター（ログエントリ条件など）を表します。

   * ログソースのノードは、常にマップの 1 番左側に表示されます。データセットにログソースが 1 つだけある場合、マップには「ログソース：*log source name*」と表示されます。 データセットに複数のログソースがある場合、マップには「*number* ログソース」と表示されます。number はログソースの個数です。例えば、データセットに 3 つのログソースがある場合、マップには「3 ログソース」と表示されます。

   * The map displays one Log Entry Condition node for each [!DNL log processing dataset include] file but only one Log Entry Condition node for transformation (if defined in the [!DNL Transformation.cfg] file). ログエントリ条件が空の場合、マップには表示されません。

* A gray node represents a field that is listed in the Fields parameter in a [!DNL Log Processing.cfg] or [!DNL Log Processing include] file.

* 青のノードは、変換を表します。
* 緑のノードは、拡張ディメンションを表します。

>[!NOTE]
>
>If your profile’s Dataset folder contains the file [!DNL Insight Transform.cfg], the dependency map shows the log sources, transformations, and exporters defined for use with Transform. 変換については、『*データセット設定ガイド*』を参照してください。

When you enable the Include [!DNL File Blocks] display option, the map displays a single blue node for all of the transformations defined in one dataset configuration file and a single green node for all of the extended dimensions defined in one dataset configuration file. この表示オプションの詳細については、「ファイルブロックを使 [用する」を参照してくださ](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)い。
