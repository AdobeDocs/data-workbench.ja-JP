---
description: プロファイルコンポーネントの識別情報の表示に関する情報です。
solution: Analytics
title: ノードの詳細の表示
topic: Data workbench
uuid: 2016a650-b021-4295-8313-d6287578ed10
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ノードの詳細の表示{#view-node-details}

プロファイルコンポーネントの識別情報の表示に関する情報です。

* ノードを右クリックして、ウィンドウの上部に識別情報を表示します。表示される識別情報は、コンポーネントのタイプで決まります。

**ログソース**

ログソースの名前と、ログソースが定義されているファイルの名前.

![](assets/vis_DependencyMap_LogSourceID.png)

**フィールド**

フィールドの名前.

![](assets/vis_DependencyMap_FieldID.png)

**変換**

変換のタイプと名前、変換が定義されているファイルの名前およびファイル内の変換の番号.

![](assets/vis_DependencyMap_TransformationID.png)

>[!NOTE]
>
>Performance information for the transformation is displayed only if the [!DNL Show Performance Data] option is enabled for the dependency map. 詳しくは、「パフォーマンスデータの [表示」を参照してくださ](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-disp-perf-data.md#concept-974e2bac3e184f0dab530e63aa4f5ecb)い。

**拡張ディメンション**

拡張ディメンションの名前とタイプ、ディメンションが定義されているファイルの名前およびファイル内のディメンションの番号.

![](assets/vis_DependencyMap_ExtendedDimensionID.png)

>[!NOTE]
>
>Performance information for the extended dimension is displayed only if the [!DNL Show Performance Data] option is enabled for the dependency map. 詳しくは、「パフォーマンスデータの [表示」を参照してくださ](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-disp-perf-data.md#concept-974e2bac3e184f0dab530e63aa4f5ecb)い。

**指標**

指標の名前.

![](assets/vis_DependencyMap_MetricID.png)

**派生ディメンション**

派生ディメンションの名前.

![](assets/vis_DependencyMap_DerivedDimensionID.png)

**フィルター**

データセット内で定義されている場合、フィルターが定義されている設定ファイルのパスとフィルターの名前.

![](assets/vis_DependencyMap_FilterID_Dataset.png)

**ワークスペースとレポート**

プロファイルのワークスペースまたはレポートのディレクトリ内でのワークスペースまたはレポートのパス.

![](assets/vis_DependencyMap_WorkspaceID.png)

**メニューオプション**

プロファイルのメニューディレクトリ内のメニュー項目のパス.

![](assets/vis_DependencyMap_MenuID.png)

**プロファイルコンポーネントの入力または出力を表示するには**

* Right-click the desired node and click **[!UICONTROL Inputs]** or **[!UICONTROL Outputs]**. 入力または出力のリストが表示されます。

