---
description: プロファイルコンポーネントの識別情報の表示に関する情報です。
title: ノードの詳細の表示
uuid: 2016a650-b021-4295-8313-d6287578ed10
exl-id: f8ce7741-8ba2-484d-ac35-5c286b65f098
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 78%

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
>依存関係マップに対して[!DNL Show Performance Data]オプションが有効になっている場合にのみ、変換のパフォーマンス情報が表示されます。 詳しくは、「[パフォーマンスデータの表示](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-disp-perf-data.md#concept-974e2bac3e184f0dab530e63aa4f5ecb)」を参照してください。

**拡張ディメンション**

拡張ディメンションの名前とタイプ、ディメンションが定義されているファイルの名前およびファイル内のディメンションの番号.

![](assets/vis_DependencyMap_ExtendedDimensionID.png)

>[!NOTE]
>
>拡張ディメンションのパフォーマンス情報は、依存関係マップに対して[!DNL Show Performance Data]オプションが有効な場合にのみ表示されます。 詳しくは、「[パフォーマンスデータの表示](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-disp-perf-data.md#concept-974e2bac3e184f0dab530e63aa4f5ecb)」を参照してください。

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

* 目的のノードを右クリックし、**[!UICONTROL Inputs]**&#x200B;または&#x200B;**[!UICONTROL Outputs]**&#x200B;をクリックします。 入力または出力のリストが表示されます。
