---
description: 引き出し線は、特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することにより、ワークスペースに追加してその要素に注意を向けるためのウィンドウです。
title: ワークスペースへの引き出し線の追加
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 49%

---

# ワークスペースへの引き出し線の追加{#adding-callouts-to-a-workspace}

{{eol}}

引き出し線は、特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することにより、ワークスペースに追加してその要素に注意を向けるためのウィンドウです。

Data Workbenchは、標準の吹き出しタイプのセットと共に提供されます。 data workbench の実装は完全にカスタマイズ可能なので、表示される使用可能な引き出し線タイプが本ガイドの記載と異なる場合があります。

デフォルトでは、Data Workbenchは次の引き出し線を提供します。

* [注釈](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [空白の折れ線グラフ](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白の散布グラフ](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白のテーブル](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [信頼性の凡例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [指標の凡例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>引き出し線内に選択を行わない限り、引き出し線は選択として機能しません（つまり、ワークスペース内の他のビジュアライゼーションには影響しません）。

引き出し線定義を追加または編集するには、 *プロファイル名*\Context\Callout フォルダー [!DNL Server] インストールフォルダー。 詳しくは、 [引き出し線の設定](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## 注釈引き出し線をビジュアライゼーションに追加するには {#section-7b6742160b3f4aed872a09c8c023f90d}

1. 引き出し線を作成する要素を右クリックし、 **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** または **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. 空白のウィンドウに、その要素への可視の接続が表示されます。

   ![](assets/client-call.png)

   グラフのビジュアライゼーションに引き出し線を追加するには、ビジュアライゼーションの下部（ベース軸）を右クリックして、メニューを表示する必要があります。

   ![](assets/visualization_callout_linegraph.png)

1. 選択に応じて、該当する手順を実行します。

   * テキスト注釈の場合は、目的のテキストを引き出し線に入力または貼り付け、必要に応じてテキストを書式設定します。「 [テキスト注釈の操作](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777).
   * 画像注釈の場合は、目的の画像をコピーし、引き出し線内で右クリックして、引き出し線に貼り付けます。「**[!UICONTROL Paste image]**」をクリックします。詳しくは、 [画像注釈の操作](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962).

## 空白のテーブル、折れ線グラフまたは散布グラフの引き出し線をビジュアライゼーションに追加するには {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. 吹き出しを作成する要素を右クリックし、 **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   以下の例は、空白のテーブルの引き出し線を示しています。

   ![](assets/vis_callout_blank_bar_graph.png)

1. 寸法を選択するには、右クリックします **[!UICONTROL None]** をクリックし、 **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >引き出し線を持つビジュアライゼーション内のディメンションを変更すると、引き出し線は、元のディメンションの要素に接続されるから、ビジュアライゼーション全体に接続されるに変わります。

## 信頼性の凡例の引き出し線をビジュアライゼーションに追加するには {#section-386d1293ddc24a0c9cccb332e20db791}

1. 吹き出しを作成する要素を右クリックし、 **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. 必要に応じて、 [!DNL Metric or Formula] フィールドに入力します。

式の構文ルールについては、 [クエリ言語構文](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f). 詳しくは、 [信頼性の凡例](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## 指標の凡例の引き出し線をビジュアライゼーションに追加するには {#section-daa6d372c22246d9827880a9d6e804d8}

1. 吹き出しを作成する要素を右クリックし、 **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. 必要に応じて、指標の凡例に指標を追加、または指標の凡例から指標を削除します。

「 [指標の凡例](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
