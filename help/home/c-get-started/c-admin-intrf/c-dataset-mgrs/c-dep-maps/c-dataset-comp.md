---
description: データセットコンポーネントに関する概念情報です。
title: データセットコンポーネント
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 57%

---

# データセットコンポーネント{#dataset-components}

{{eol}}

データセットコンポーネントに関する概念情報です。

下の図に、ノードがデータセットのログソース、フィールド、変換、拡張ディメンションを表している依存関係マップを示します。

![](assets/vis_DependencyMap.png)

* 黄緑のノードは、データセット内で定義されている 1 つ以上のログソースまたはフィルター（ログエントリ条件など）を表します。

   * ログソースのノードは、常にマップの 1 番左側に表示されます。データセットにログソースが 1 つだけある場合、マップには「ログソース：*log source name*」と表示されます。 データセットに複数のログソースがある場合、マップには「*number* ログソース」と表示されます。number はログソースの個数です。例えば、データセットに 3 つのログソースがある場合、マップには「3 ログソース」と表示されます。

   * マップには、それぞれに対して 1 つの「Log Entry Condition」ノードが表示されます [!DNL log processing dataset include] ファイルに書き込まれるが、変換対象の Log Entry Condition ノードは 1 つだけ ( [!DNL Transformation.cfg] ファイル ) です。 ログエントリ条件が空の場合、マップには表示されません。

* 灰色のノードは、 [!DNL Log Processing.cfg] または [!DNL Log Processing include] ファイル。

* 青のノードは、変換を表します。
* 緑のノードは、拡張ディメンションを表します。

>[!NOTE]
>
>プロファイルの Dataset フォルダーに [!DNL Insight Transform.cfg]依存関係マップには、変換で使用するために定義されたログソース、変換、エクスポーターが表示されます。 変換については、『*データセット設定ガイド*』を参照してください。

「以下を含む」を有効にした場合 [!DNL File Blocks] 「表示」オプションを選択すると、1 つのデータセット設定ファイルで定義されたすべての変換に対して 1 つの青いノードが表示され、1 つのデータセット設定ファイルで定義されたすべての拡張ディメンションに対して 1 つの緑のノードが表示されます。 この表示オプションについて詳しくは、 [ファイルブロックの操作](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
