---
description: 引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。
title: 引き出し線の設定
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 41%

---

# 引き出し線の設定{#configure-a-callout}

引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。

引き出し線を追加または編集するには、プロファイルー\*プロファイルー名*\Context\Callout folder of the [!DNL Server]のインストールフォルダーに保存されている引き出し線ファイルを設定します。 ワークシートのビジュアライゼーション内の特定の指標に注意を向ける引き出し線は、指標引き出し線と呼ばれます。指標引き出し線ファイルは、プロファイル\*プロファイル名*\Context\Metric Callout folderに保存されます。

引き出し線または指標引き出し線をビジュアライゼーションに追加する手順については、[ワークスペースへの引き出し線の追加](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)を参照してください。

**新しいタイプの引き出し線を作成するには**

1. 任意のワークスペース内に、新しい引き出し線タイプに表示するデータを含むビジュアライゼーションを作成します。例えば、引き出し線をテーブルにしたい場合は、目的の指標とディメンションを表示するテーブルのビジュアライゼーションを作成します。
1. 引き出し線ウィンドウの上の枠を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
1. [!DNL Save]ウィンドウで![](assets/btn_folder_up.png)をクリックし、**[!UICONTROL Context]**&#x200B;を重複クリックしてから&#x200B;**[!UICONTROL Callout]**&#x200B;を重複クリックします。 [!DNL File Name]フィールドにファイル名を入力し、**[!UICONTROL Save]**&#x200B;をクリックします。 引き出し線ファイルは、User\*workingプロファイル名*\Context\Callout folderに保存されます。

   >[!NOTE]
   >
   >引き出し線に名前を付ける場合は、ビジュアライゼーションのタイプと、表示される指標とディメンションを反映するわかりやすい名前を選択します。 例えば、Day（日）ディメンションに対する Sessions（セッション）指標を示すテーブルのビジュアライゼーションから引き出し線を作成する場合、その引き出し線に「Sessions by Day Table（日別のセッションテーブル）」という名前を付けられます。

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Context]**&#x200B;をクリックし、**[!UICONTROL Callout]**&#x200B;をクリックします。 このフォルダーには、既存の引き出し線タイプを定義するすべてのビジュアライゼーションファイル([!DNL .vw])が含まれています。

   1. [!DNL User]列の新しい引き出し線のファイル名の横のチェックマークを右クリックし、**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*&#x200B;をクリックします。

**引き出し線を指標引き出し線に変更するには**

1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Context]**&#x200B;をクリックし、**[!UICONTROL Callout]**&#x200B;をクリックします。 このフォルダーには、既存の引き出し線タイプを定義するすべてのビジュアライゼーションファイル([!DNL .vw])が含まれています。

1. 変更する引き出し線のタイプのファイル名の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 ファイルがローカルコンピューターにダウンロードされると、[!DNL User] 列にチェックマークが表示されます。

1. [!DNL User]列のファイル名の横のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL In Notepad]**&#x200B;をクリックします。

1. 引き出し線ファイル内の[!DNL metric_y = ref:]エントリを探し、既存の値をMetricという語で置き換えます。 以下のファイルの一部でハイライトされているテキストは、Metric という語を挿入する場所を示しています。

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

1. クリック **[!UICONTROL File]** > **[!UICONTROL Save As]**. **[!UICONTROL Save As]**&#x200B;ウィンドウで1回クリックし、次に&#x200B;**[!UICONTROL Metric Callout]**&#x200B;を重複クリックします。 [!DNL File Name]フィールドにファイル名を入力し、**[!UICONTROL Save]**&#x200B;をクリックします。 指標引き出し線ファイルは、User\*workingプロファイル名*\Context\Metric Callout folderに保存されます。

1. （オプション）作業プロファイルのすべてのユーザーがこの指標引き出し線を使用できるようにするには、[!DNL Profile Manager]列で、[!DNL User]列のファイル名の横のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]***&#x200B;をクリックします。
