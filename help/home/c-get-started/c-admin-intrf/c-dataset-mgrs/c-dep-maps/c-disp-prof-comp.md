---
description: プロファイルのデータセットコンポーネント、クエリーモデルコンポーネントまたはワークスペース、レポート、メニューオプションおよびグローブレイヤーを依存関係マップに表示できます。
title: プロファイルコンポーネントの表示
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
exl-id: 9d0aea02-cc24-43c2-afb8-e11ebd80e193
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 78%

---

# プロファイルコンポーネントの表示{#display-profile-components}

{{eol}}

プロファイルのデータセットコンポーネント、クエリーモデルコンポーネントまたはワークスペース、レポート、メニューオプションおよびグローブレイヤーを依存関係マップに表示できます。

**表示するコンポーネントを選択するには**

1. 依存関係マップ内で右クリックし、 **[!UICONTROL Display]**.
1. マップ上に表示するための以下のオプションを 1 つ以上選択します。有効にした各表示オプションの左側には X が表示されます。

   * データセットコンポーネントを表示するには「**データセット**」を選択します。「[データセットコンポーネント](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293)」を参照してください。データセットのコンポーネントを表示する場合は、次のオプションを使用できます。 [!DNL Include File Blocks] 地図上で 詳しくは、 [ファイルブロックの操作](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * クエリーモデルコンポーネントを表示するには「**クエリーモデル**」を選択します。「[クエリーモデルコンポーネント](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)」を参照してください。

   * ワークスペース、レポート、メニューオプションおよびグローブレイヤーを表示するには「**ワークスペースとビジュアライゼーション**」を選択します。「[ワークスペースとビジュアライゼーション](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921)」を参照してください。このオプションは、 [!DNL Query Model] 「表示」オプションが有効になっている。

>[!NOTE]
>
>この [!DNL Query Model] 次を選択した場合、「表示」オプションは有効になりません： [!DNL Workspaces and Visualizations] 「表示」オプションを選択すると、エラーメッセージが表示されます。

マップ上にすべてのノードが表示されていない場合は、マップを移動、ズームインまたはズームアウトして、マップ全体を表示したり、特定のセクションにフォーカスしたりできます。ズームについて詳しくは、「[ビジュアライゼーションへのズーム](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530)」を参照してください。

ノードをクリックすると、そのノードに依存しているすべてのノードと、そのノードが依存しているすべてのノードがハイライトされ、ノード名が表示されます。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>依存関係マップ内でハイライト表示されているパスは、選択範囲を構成していません。

ノードを右クリックすると、マップに表示されている各コンポーネントに関する識別情報を確認したり、メニューオプションを選択して、コンポーネントに関する詳細を表示したり、コンポーネントを編集したりできます。さらに、テキスト検索を実行し、変換と拡張ディメンションに関するパフォーマンスデータを表示できます。
