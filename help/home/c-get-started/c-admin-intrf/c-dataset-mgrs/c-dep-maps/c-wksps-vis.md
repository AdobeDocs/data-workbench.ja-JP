---
description: ワークスペースとビジュアライゼーションに関する概念情報です。
title: ワークスペースとビジュアライゼーション
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 47%

---

# ワークスペースとビジュアライゼーション{#workspaces-and-visualizations}

ワークスペースとビジュアライゼーションに関する概念情報です。

次の図に依存関係マップを示します。このマップのノードは、プロファイルで定義されたワークスペース、レポート、メニューオプションおよびグローブレイヤーを表します。このオプションは、[!DNL Query Model]表示オプションが有効な場合にのみ機能します。

>[!NOTE]
>
>[!DNL Workspaces and Visualizations]表示オプションを選択したときに[!DNL Query Model]表示オプションが有効になっていない場合は、エラーメッセージが表示されます。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色のノードは、ワークスペースまたはレポートを表します。
* 黄緑色のノードは、メニューオプションを表します。
* 赤いノードは、依存関係の破損または循環などエラーのあるワークスペース、レポート、メニューオプションまたはグローブレイヤーを表します。

>[!NOTE]
>
>依存関係マップは非循環依存関係に対応するように設計されているので、循環依存関係に関係するノードがマップ上に正しく表示されない場合があります。 「[!DNL Search]」テキストボックスに「circular dependency」と入力して、循環依存関係を検索できます。 [!DNL Search]機能の詳細については、「[マップ内での検索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)」を参照してください。

マップ上の他のノードの説明については、[クエリーモデルコンポーネント](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)を参照してください。
