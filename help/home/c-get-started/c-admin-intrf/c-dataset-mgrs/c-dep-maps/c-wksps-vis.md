---
description: ワークスペースとビジュアライゼーションに関する概念情報です。
solution: Analytics
title: ワークスペースとビジュアライゼーション
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Workspaces and visualizations{#workspaces-and-visualizations}

ワークスペースとビジュアライゼーションに関する概念情報です。

次の図に依存関係マップを示します。このマップのノードは、プロファイルで定義されたワークスペース、レポート、メニューオプションおよびグローブレイヤーを表します。This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>表示オプション [!DNL Query Model] を選択したときに表示オプションが有効になっていな [!DNL Workspaces and Visualizations] い場合は、エラーメッセージが表示されます。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色のノードは、ワークスペースまたはレポートを表します。
* 黄緑色のノードは、メニューオプションを表します。
* 赤いノードは、依存関係の破損または循環などエラーのあるワークスペース、レポート、メニューオプションまたはグローブレイヤーを表します。

>[!NOTE]
>
>依存関係マップは非循環依存関係を収容するように設計されているので、循環依存関係に含まれるノードはマップ上で正しく表示されない場合があります。 You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. この機能の詳細については、「 [!DNL Search] マップ内で検索 [する」を参照してください](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

マップ上の他のノードの説明は、「クエリーモデルのコンポーネ [ント」を参照してくださ](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)い。
