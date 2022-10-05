---
description: クエリーモデルコンポーネントに関する概念情報です。
title: クエリモデルコンポーネント
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 70%

---

# クエリモデルコンポーネント{#query-model-components}

{{eol}}

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
>依存関係マップは非循環依存関係に対応するように設計されているので、循環依存関係に関係するノードがマップ上に正しく表示されない場合があります。 循環依存関係を検索するには、 [!DNL Search] テキストボックス 詳しくは、 [!DNL Search] 機能： [マップ内での検索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
