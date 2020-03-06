---
description: サイドバーを使用して、よく使用する機能にアクセスしたり、ビジュアライゼーションを保持したままワークスペース間を移動したりできます。
solution: Analytics
title: サイドバーの設定
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# サイドバーの設定{#configure-the-sidebar}

サイドバーを使用して、よく使用する機能にアクセスしたり、ビジュアライゼーションを保持したままワークスペース間を移動したりできます。

管理者は、様々なユーザーグループに合わせてサイドバーをカスタマイズし、プロファイルと共にデプロイすることができます。

サイドバーは、フィルターやローカルオーバーライドを追跡できるようにする理想的なツールです。サイドバーを使用したくない場合は、非表示にできます。

## Add visualizations to the sidebar {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Data Workbenchを起動します。
1. In the sidebar, click **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Data Workbenchの標準インストールでは、次のサイドバーパネルを使用できます。 以下の特定のプロファイルでは、その他の項目を使用できる場合があります。

   * **選択パネル：** 現在のワークスペースでアクティブな選択範囲を把握できます。 The [!DNL Selections Panel] updates whenever you make a new selection. **[!UICONTROL x]** をクリックして、選択範囲をクリアできます。See [Making Selections in Visualizations](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) for information about how to select data.
   * **フィルターパネル：** 保存したフィルターの読み込みと適用を簡単にします。 複数のフィルターを読み込み、各フィルターの横のチェックボックスをクリックして、個別に有効/無効にできます。「 [フィルターエディター](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **ローカルオーバーライドパネル：** このパネルには、プロファイル内に存在し、プロファイルの個人コピーで変更された指標、ディメンションおよびフィルターが表示されます。 自分のクライアントと他のユーザーのクライアントでデータの表示が異なる可能性に関して注意を促すのに役立ちます。When you save changes in a metric, dimension, or filter to the server, the override is removed from the [!DNL Local Overrides panel]. If you click an override and then click **[!UICONTROL Revert to Server]**, the local override is removed and the item reverts to the shared version.
   * **指標の凡例：** 指標の凡例を追加します。 [!DNL Metric legends] プロファイルに関連するベースライン指標と、データセット(または、現在の選択範囲（作成されている場合）に関連する統計を表示できます。 指標の凡 [例を参照してください](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
   * **色凡例：** 色凡例を追加します。 You can color-code visualizations by metrics, such as Conversion and Retention, and use them in almost every [!DNL Workspace]. ビジネス指標を色にリンクすると、異常、例外、トレンドを見極めやすくなります。「[色凡例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)」を参照してください。
   * **テキスト注釈：** メモパネルを追加します。 [!DNL Text annotations] は、任意のテキストを入力して、説明情報やコメントをに追加できるウィンドウで [!DNL Workspace]す。 See [Working with Text Annotations](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * **表：** テーブルを追加します。 テーブルには、1 つ以上のデータのディメンションにまたがる 1 つ以上の指標を表示できます。「 [テーブル](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **開く：** 保存したファイルを開きます。

## サイドバーパネルを開く {#section-cbc8e57491854274a577d47a48c306b8}

保存した場所またはクリップボードから、サイドバーのビジュアライゼーションを開けます。

1. サイドバーで、/をクリッ **[!UICONTROL Add]** クしま **[!UICONTROL Open]**&#x200B;す。
1. Click **[!UICONTROL File]** to locate the [!DNL .vw] file of the panel you want to add, or click **[!UICONTROL Last Closed Window]**, which pulls the visualization from the clipboard.

   Additionally, you can click **[!UICONTROL From Clipboard]** to paste a visualization that has been copied to the clipboard. 「[サイドバーパネルのコピー](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)」を参照してください。

## サイドバーパネルのコピー {#section-720ae057632a4b8dbb94412e06a370b1}

1. Right-click the panel’s top border, then click **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. パネルを貼り付けるには、//をク **[!UICONTROL Add]** リック **[!UICONTROL Open]** しま **[!UICONTROL From Clipboard]**&#x200B;す。

## サイドバーパネルの保存 {#section-fb19936b12704fb0a4c592abb579db1d}

On an sidebar panel, right click in the title bar and click **[!UICONTROL Save]**.

同様に、保存されているサイドバーのビジュアライゼーションを開くこともできます。Data Workbench saves the visualization as a [!DNL .vw] file at the location you specify.

## Revert to the Default Sidebar {#section-4d14b8771ad747bba799876267f24831}

サイドバーで、/をクリッ **[!UICONTROL Options]** クしま **[!UICONTROL Revert]**&#x200B;す。

When you close Data Workbench, the system saves the current sidebar configuration in the [!DNL sidebar.vw] file in the user profile. When you open Data Workbench, the system loads the [!DNL sidebar.vw] file from the user profile, rather than a parent profile.

デフォルトのサイドバーまたは以前保存したサイドバーに戻すことができます。以前保存したサイドバーはユーザープロファイルから削除され、親プロファイルからサイドバーが再読み込みされます。Administrators can replace the default (parent) sidebar with a local sidebar by uploading it from the [!DNL Profile Manager].

## Customize the More Status Panel File {#section-8d502f3b59cc4331966edec05e896ce1}

System administrators can build formulas in the [!DNL More Status Panel.vw]. This places contextual words around metric and dimension values, and displays the results in the [!DNL More Status panel] in the sidebar.

To display the [!DNL More Status panel] in the sidebar, click the arrows shown in the following example.

![](assets/more_status_panel_arrows.png)

以下の手順は、データセットに含まれる日数を示す、カスタマイズされたステータスを作成する方法の簡単な例を示しています。

1. で、[!UICONTROL [!DNL Profile Manager]サイ **ドバー\]をクリックします**。

1. In the [!DNL Base_5_3*] column, make a local copy of the [!DNL More Status Panel.vw] file.

   To do so, right-click the file check mark and click **[!UICONTROL Make Local]**.

1. ファイルをメモ [!DNL More Status Panel.vw] 帳で開くか、メ [!DNL .vw] モ帳で [!DNL Editor] 開きます。

   ![](assets/more_status_panel_file.png)

1. Complete the [!DNL Context] and [!DNL Items] fields in the [!DNL Editor]. See [Query Language Syntax](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) for guidelines about syntax.

1. ファイルを保存します。

   前述の例の値は、次のように表示されるステータス数式になります。

   ![](assets/more_status_panel.png)

