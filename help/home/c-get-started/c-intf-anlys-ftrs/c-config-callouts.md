---
description: 引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。
title: 引き出し線の設定
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 41%

---

# 引き出し線の設定{#configure-a-callout}

{{eol}}

引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。

引き出し線を追加または編集するには、 [!DNL Server] インストールフォルダー。 ワークシートのビジュアライゼーション内の特定の指標に注意を向ける引き出し線は、指標引き出し線と呼ばれます。指標引き出し線ファイルは、 Profiles\*profile name*\Context\Metric Callout フォルダーに保存されます。

引き出し線または指標引き出し線をビジュアライゼーションに追加する手順については、 [ワークスペースへの引き出し線の追加](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**新しいタイプの引き出し線を作成するには**

1. 任意のワークスペース内に、新しい引き出し線タイプに表示するデータを含むビジュアライゼーションを作成します。例えば、引き出し線をテーブルにしたい場合は、目的の指標とディメンションを表示するテーブルのビジュアライゼーションを作成します。
1. 吹き出しウィンドウの上の枠を右クリックし、 **[!UICONTROL Save]**.
1. 内 [!DNL Save] ウィンドウ、クリック ![](assets/btn_folder_up.png)，ダブルクリック **[!UICONTROL Context]**&#x200B;をクリックし、ダブルクリックします。 **[!UICONTROL Callout]**. 内 [!DNL File Name] フィールドにファイル名を入力し、 **[!UICONTROL Save]**. 引き出し線ファイルは、User\*working profile name*\Context\Callout フォルダーに保存されます。

   >[!NOTE]
   >
   >引き出し線に名前を付ける場合は、ビジュアライゼーションのタイプと、表示される指標およびディメンションを反映したわかりやすい名前を選択します。 例えば、Day（日）ディメンションに対する Sessions（セッション）指標を示すテーブルのビジュアライゼーションから引き出し線を作成する場合、その引き出し線に「Sessions by Day Table（日別のセッションテーブル）」という名前を付けられます。

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Context]**&#x200B;を選択し、「 **[!UICONTROL Callout]**. このフォルダーには、すべてのビジュアライゼーションファイル ( [!DNL .vw]) を使用して、既存の引き出し線タイプを定義します。

   1. 内の新しい引き出し線のファイル名の横にあるチェックマークを右クリックします。 [!DNL User] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**引き出し線を指標引き出し線に変更するには**

1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Context]**&#x200B;を選択し、「 **[!UICONTROL Callout]**. このフォルダーには、すべてのビジュアライゼーションファイル ( [!DNL .vw]) を使用して、既存の引き出し線タイプを定義します。

1. 変更する吹き出しの種類のファイル名の横にあるチェックマークを右クリックし、 **[!UICONTROL Make Local]**. ファイルがローカルコンピューターにダウンロードされると、[!DNL User] 列にチェックマークが表示されます。

1. ファイル名の横にあるチェックマークを右クリックします。 [!DNL User] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. を [!DNL metric_y = ref:] 引き出し線ファイルにエントリし、既存の値を Metric という単語に置き換えます。 以下のファイルの一部でハイライトされているテキストは、Metric という語を挿入する場所を示しています。

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. クリック **[!UICONTROL File]** > **[!UICONTROL Save As]**. 内 **[!UICONTROL Save As]** ウィンドウを開き、1 回クリックしてからダブルクリックします。 **[!UICONTROL Metric Callout]**. 内 [!DNL File Name] フィールドにファイル名を入力し、 **[!UICONTROL Save]**. 指標引き出し線ファイルは、User\*working profile name*\Context\Metric Callout フォルダーに保存されます。

1. （オプション）作業プロファイルのすべてのユーザーがこの指標引き出し線を使用できるようにするには、 [!DNL Profile Manager]を選択し、 [!DNL User] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
