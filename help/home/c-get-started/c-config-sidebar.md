---
description: サイドバーを使用して、よく使用する機能にアクセスしたり、ビジュアライゼーションを保持したままワークスペース間を移動したりできます。
title: サイドバーの設定
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
exl-id: 75ccc869-8ced-4beb-b3d7-ed7febe347f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 37%

---

# サイドバーの設定{#configure-the-sidebar}

サイドバーを使用して、よく使用する機能にアクセスしたり、ビジュアライゼーションを保持したままワークスペース間を移動したりできます。

管理者は、様々なユーザーグループに合わせてサイドバーをカスタマイズし、プロファイルと共にデプロイすることができます。

サイドバーは、フィルターやローカルオーバーライドを追跡できるようにする理想的なツールです。サイドバーを使用したくない場合は、非表示にできます。

## サイドバーにビジュアライゼーションを追加します。{#section-666f70a405db4f8d8eaffa567ffcac06}

1. ローンチData Workbench。
1. サイドバーで、 **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*&#x200B;をクリックします。 例：[!DNL Selections Panel]、[!DNL Filters Panel]、[!DNL Table]。

   Data Workbenchの標準インストールでは、次のサイドバーパネルを使用できます。 以下の特定のプロファイルでは、その他の項目を使用できる場合があります。

   * **選択パネル：** 現在のワークスペースでアクティブな選択範囲を把握できます。[!DNL Selections Panel]は、新しい選択を行うたびに更新されます。 **[!UICONTROL x]** をクリックして、選択範囲をクリアできます。データの選択方法について詳しくは、[ビジュアライゼーションでの選択](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)を参照してください。
   * **フィルターパネル：** 保存されたフィルターの読み込みと適用が簡単になります。複数のフィルターを読み込み、各フィルターの横のチェックボックスをクリックして、個別に有効/無効にできます。「 [フィルターエディター](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **ローカル上書きパネル：** このパネルには、プロファイルに存在し、プロファイルの個人コピーで変更された指標、ディメンション、フィルターが表示されます。自分のクライアントと他のユーザーのクライアントでデータの表示が異なる可能性に関して注意を促すのに役立ちます。指標、ディメンション、フィルターの変更をサーバーに保存すると、上書きは[!DNL Local Overrides panel]から削除されます。 上書きをクリックして&#x200B;**[!UICONTROL Revert to Server]**&#x200B;をクリックすると、ローカルの上書きが削除され、項目が共有バージョンに戻ります。
   * **指標の凡例：** 指標の凡例を追加します。[!DNL Metric legends] を使用すると、プロファイルに関連するベースライン指標と、データセットに関連する統計（作成済みの場合は現在の選択）を確認できます。[指標の凡例](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)を参照してください。
   * **色凡例：** 色凡例を追加します。コンバージョンや定着などの指標別にビジュアライゼーションを色分けし、ほぼすべての[!DNL Workspace]で使用できます。 ビジネス指標を色にリンクすると、異常、例外、トレンドを見極めやすくなります。「[色凡例](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)」を参照してください。
   * **テキスト注釈：** メモパネルを追加します。[!DNL Text annotations] は、任意のテキストを入力して、説明情報やコメントをに追加できるウィンドウで [!DNL Workspace]す。[テキスト注釈の操作](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)を参照してください。
   * **テーブル：** テーブルを追加します。テーブルには、1 つ以上のデータのディメンションにまたがる 1 つ以上の指標を表示できます。[テーブル](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f)を参照してください。
   * **開く：** 保存したファイルを開きます。

## サイドバーパネル{#section-cbc8e57491854274a577d47a48c306b8}を開きます。

保存した場所またはクリップボードから、サイドバーのビジュアライゼーションを開けます。

1. サイドバーで、 **[!UICONTROL Add]** > **[!UICONTROL Open]**&#x200B;をクリックします。
1. **[!UICONTROL File]**&#x200B;をクリックして、追加するパネルの[!DNL .vw]ファイルを探すか、「**[!UICONTROL Last Closed Window]**」をクリックしてクリップボードからビジュアライゼーションを取り込みます。

   さらに、**[!UICONTROL From Clipboard]**&#x200B;をクリックして、クリップボードにコピーしたビジュアライゼーションを貼り付けることもできます。 「[サイドバーパネルのコピー](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)」を参照してください。

## サイドバーパネルのコピー {#section-720ae057632a4b8dbb94412e06a370b1}

1. パネルの上の枠を右クリックし、 **[!UICONTROL Copy]** > **[!UICONTROL Window]**&#x200B;をクリックします。
1. パネルを貼り付けるには、**[!UICONTROL Add]** / **[!UICONTROL Open]** / **[!UICONTROL From Clipboard]**&#x200B;をクリックします。

## サイドバーパネルの保存 {#section-fb19936b12704fb0a4c592abb579db1d}

サイドバーパネルで、タイトルバーを右クリックし、「**[!UICONTROL Save]**」をクリックします。

同様に、保存されているサイドバーのビジュアライゼーションを開くこともできます。Data Workbenchは、ビジュアライゼーションを[!DNL .vw]ファイルとして指定した場所に保存します。

## デフォルトのサイドバーに戻る{#section-4d14b8771ad747bba799876267f24831}

サイドバーで、 **[!UICONTROL Options]** > **[!UICONTROL Revert]**&#x200B;をクリックします。

Data Workbenchを閉じると、現在のサイドバー設定がユーザープロファイルの[!DNL sidebar.vw]ファイルに保存されます。 Data Workbenchを開くと、親プロファイルではなく、ユーザープロファイルから[!DNL sidebar.vw]ファイルが読み込まれます。

デフォルトのサイドバーまたは以前保存したサイドバーに戻すことができます。以前保存したサイドバーはユーザープロファイルから削除され、親プロファイルからサイドバーが再読み込みされます。管理者は、[!DNL Profile Manager]からアップロードすることで、デフォルト（親）のサイドバーをローカルのサイドバーに置き換えることができます。

## その他のステータスパネルファイル{#section-8d502f3b59cc4331966edec05e896ce1}をカスタマイズします。

システム管理者は、[!DNL More Status Panel.vw]に数式を作成できます。 これにより、指標とディメンションの値に関して状況に応じた単語が配置され、結果がサイドバーの[!DNL More Status panel]に表示されます。

サイドバーに[!DNL More Status panel]を表示するには、次の例に示す矢印をクリックします。

![](assets/more_status_panel_arrows.png)

以下の手順は、データセットに含まれる日数を示す、カスタマイズされたステータスを作成する方法の簡単な例を示しています。

1. [!DNL Profile Manager]で、「**[!UICONTROL Sidebar\]**」をクリックします。

1. [!DNL Base_5_3*]列で、[!DNL More Status Panel.vw]ファイルのローカルコピーを作成します。

   ファイルのチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。

1. [!DNL .vw] [!DNL Editor]またはメモ帳で[!DNL More Status Panel.vw]ファイルを開きます。

   ![](assets/more_status_panel_file.png)

1. [!DNL Editor]の[!DNL Context]フィールドと[!DNL Items]フィールドに入力します。 構文に関するガイドラインについては、[クエリー言語構文](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)を参照してください。

1. ファイルを保存します。

   前述の例の値は、次のように表示されるステータス数式になります。

   ![](assets/more_status_panel.png)
