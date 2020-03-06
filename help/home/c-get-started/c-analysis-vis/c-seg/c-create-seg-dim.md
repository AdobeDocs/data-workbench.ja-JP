---
description: セグメントディメンションを作成するには、まずワークスペース内に選択範囲を作成してから、セグメントをビジュアライゼーションに追加します。
solution: Analytics
title: セグメントディメンションの作成
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Create a segment dimensions{#create-a-segment-dimensions}

セグメントディメンションを作成するには、まずワークスペース内に選択範囲を作成してから、セグメントをビジュアライゼーションに追加します。

**セグメントディメンションを作成するには**

1. セグメントのビジュアライゼーションをワークスペースに追加します。次に例を示します。

   ![](assets/vis_Segment.png)

1. セグメントの定義に使用するワークスペースにビジュアライゼーションを追加してから、目的の選択範囲を作成してセグメントを定義します。
1. In the segment visualization, right-click the label of the segment after which you want the new segment to be added and click **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >新しい最初のセグメントを作成するには、ラベルを右クリック **[!UICONTROL Segments]** し、をクリックしま **[!UICONTROL Add Segment]**&#x200B;す。

   ![](assets/vis_SegmentNew.png)

   新しいセグメント（名前は「新規セグメント」）がビジュアライゼーションに表示されます。「その他」セグメントは、定義済みのセグメントに含まれないすべてのデータを表します。事実上、これがデータセットのデータとセグメントのデータの違いになります。

1. Right-click the newly created segment and click **[!UICONTROL Rename Segment]**.
1. 新しいセグメントを説明する名前を名前フィールドに入力します。

   >[!NOTE]
   >
   >If a metric value, such as a particular visitor in [!DNL Site], meets the criteria of multiple segments, the metric value is included in only the first listed segment that it matches.

**セグメントディメンションを保存するには**

1. Right-click the Segments label and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears. デフォルトの保存場所は、User\*profile name*\Dimensionsフォルダーです。
1. In the [!DNL File name] field, type a descriptive name for the segments that you are saving as a dimension and click **[!UICONTROL Save]**.

ビジュアライゼーションを操作しているときはいつでも、このセグメントディメンションにアクセスできます。セグメントエクスポート機能を使用して、保存したディメンション内の要素に関連付けられたデータをエクスポートすることもできます。

セグメントエクスポート機能とニーズに合わせた設定方法について詳しくは、「 [エクスポート用にセグメントを設定する](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
