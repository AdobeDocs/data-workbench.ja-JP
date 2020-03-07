---
description: クエリーモデルコンポーネントに関する概念情報です。
solution: Analytics
title: クエリーモデルコンポーネント
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Query model components{#query-model-components}

クエリーモデルコンポーネントに関する概念情報です。

以下の図は、ノードがプロファイル内の Dimensions フォルダー、Metrics フォルダー、Filters フォルダーに定義されているクエリーモデルの指標、派生ディメンション、フィルターおよび何らかの方法で関連付けられたデータセット内で定義されている拡張ディメンションを表す依存関係マップを示しています。

![](assets/vis_DependencyMap_QueryModel.png)

* 黄緑のノードはフィルターを表します。
* 紫のノードは指標を表します。
* 青緑のノードは派生ディメンションを表します。
* 緑のノードは拡張ディメンション（データセット内で定義）を表します。
* 赤のノードは、依存関係が壊れているか循環している、または他のエラーがある指標、派生ディメンション、フィルターを表します。

>[!NOTE]
>
>依存関係マップは非循環依存関係を収容するように設計されているので、循環依存関係に含まれるノードはマップ上で正しく表示されない場合があります。 You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. この機能の詳細については、「 [!DNL Search] マップ内で検索 [する」を参照してください](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

