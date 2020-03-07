---
description: プロファイルのデータセットコンポーネント、クエリーモデルコンポーネントまたはワークスペース、レポート、メニューオプションおよびグローブレイヤーを依存関係マップに表示できます。
solution: Analytics
title: 縦断コンポーネントを表示
topic: Data workbench
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 縦断コンポーネントを表示{#display-profile-components}

プロファイルのデータセットコンポーネント、クエリーモデルコンポーネントまたはワークスペース、レポート、メニューオプションおよびグローブレイヤーを依存関係マップに表示できます。

**表示するコンポーネントを選択するには**

1. Right-click within the dependency map and click **[!UICONTROL Display]**.
1. マップ上に表示するための以下のオプションを 1 つ以上選択します。有効にした各表示オプションの左側には X が表示されます。

   * データセットコンポーネントを表示するには「**データセット**」を選択します。「[データセットコンポーネント](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293)」を参照してください。If you choose to display the dataset components, you have the option to [!DNL Include File Blocks] on the map. See [Working with File Blocks](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * クエリーモデルコンポーネントを表示するには「**クエリーモデル**」を選択します。「[クエリーモデルコンポーネント](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)」を参照してください。

   * ワークスペース、レポート、メニューオプションおよびグローブレイヤーを表示するには「**ワークスペースとビジュアライゼーション**」を選択します。「[ワークスペースとビジュアライゼーション](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921)」を参照してください。This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>表示オプション [!DNL Query Model] を選択したときに表示オプションが有効になっていな [!DNL Workspaces and Visualizations] い場合は、エラーメッセージが表示されます。

マップ上にすべてのノードが表示されていない場合は、マップを移動、ズームインまたはズームアウトして、マップ全体を表示したり、特定のセクションにフォーカスしたりできます。ズームについて詳しくは、「[ビジュアライゼーションへのズーム](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530)」を参照してください。

ノードをクリックすると、そのノードに依存しているすべてのノードと、そのノードが依存しているすべてのノードがハイライトされ、ノード名が表示されます。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>依存関係マップ内でハイライトされたパスは、選択を構成しません。

ノードを右クリックすると、マップに表示されている各コンポーネントに関する識別情報を確認したり、メニューオプションを選択して、コンポーネントに関する詳細を表示したり、コンポーネントを編集したりできます。さらに、テキスト検索を実行し、変換と拡張ディメンションに関するパフォーマンスデータを表示できます。
