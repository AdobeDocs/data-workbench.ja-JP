---
description: セグメントディメンションを作成するには、まずワークスペース内に選択範囲を作成してから、セグメントをビジュアライゼーションに追加します。
title: セグメントディメンションの作成
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 64%

---

# セグメントディメンションの作成{#create-a-segment-dimensions}

セグメントディメンションを作成するには、まずワークスペース内に選択範囲を作成してから、セグメントをビジュアライゼーションに追加します。

**セグメントディメンションを作成するには**

1. セグメントのビジュアライゼーションをワークスペースに追加します。次に例を示します。

   ![](assets/vis_Segment.png)

1. セグメントの定義に使用するワークスペースにビジュアライゼーションを追加してから、目的の選択範囲を作成してセグメントを定義します。
1. セグメントのビジュアライゼーションで、新しいセグメントを追加する後のセグメントのラベルを右クリックし、「**[!UICONTROL Add Segment]**」をクリックします。

   >[!NOTE]
   >
   >新しい最初のセグメントを作成するには、**[!UICONTROL Segments]**&#x200B;ラベルを右クリックし、**[!UICONTROL Add Segment]**&#x200B;をクリックします。

   ![](assets/vis_SegmentNew.png)

   新しいセグメント（名前は「新規セグメント」）がビジュアライゼーションに表示されます。「その他」セグメントは、定義済みのセグメントに含まれないすべてのデータを表します。事実上、これがデータセットのデータとセグメントのデータの違いになります。

1. 新しく作成されたセグメントを右クリックし、「**[!UICONTROL Rename Segment]**」をクリックします。
1. 新しいセグメントを説明する名前を名前フィールドに入力します。

   >[!NOTE]
   >
   >[!DNL Site]の特定の訪問者などの指標の値が複数のセグメントの条件を満たす場合、その指標の値は、一致する最初にリストされたセグメントにのみ含まれます。

**セグメントディメンションを保存するには**

1. セグメントラベルを右クリックし、「**[!UICONTROL Save Dimension]**」をクリックします。 [!DNL Save Dimension As]ウィンドウが表示されます。 デフォルトの保存場所は、User\*profile name*\profilesフォルダーです。Dimension
1. 「[!DNL File name]」フィールドに、ディメンションとして保存するセグメントのわかりやすい名前を入力し、「**[!UICONTROL Save]**」をクリックします。

ビジュアライゼーションを操作しているときはいつでも、このセグメントディメンションにアクセスできます。セグメントエクスポート機能を使用して、保存したディメンション内の要素に関連付けられたデータをエクスポートすることもできます。

セグメントエクスポート機能とニーズに合わせた設定方法について詳しくは、「 [エクスポート用にセグメントを設定する](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
