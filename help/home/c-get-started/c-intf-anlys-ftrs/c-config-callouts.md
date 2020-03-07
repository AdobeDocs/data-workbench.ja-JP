---
description: 引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。
solution: Analytics
title: 引き出し線の設定
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 引き出し線の設定{#configure-a-callout}

引き出し線は、ビジュアライゼーション内の特定のディメンション要素からなるバーチャルな選択範囲を使用して新しいビジュアライゼーションを作成することによって、特定のディメンション要素に注意を向けます。

You can add or edit callouts by configuring the callout files stored in a Profiles\*profile name*\Context\Callout folder of the [!DNL Server] installation folder. ワークシートのビジュアライゼーション内の特定の指標に注意を向ける引き出し線は、指標引き出し線と呼ばれます。指標引き出し線ファイルは、Profiles\*profile name*\Context\Metric Callout folderフォルダーに保存されます。

引き出し線または指標引き出し線をビジュアライゼーションに追加する手順については、「ワークスペー [スへの引き出し線の追加」を参照してくださ](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)い。

**新しいタイプの引き出し線を作成するには**

1. 任意のワークスペース内に、新しい引き出し線タイプに表示するデータを含むビジュアライゼーションを作成します。例えば、引き出し線をテーブルにしたい場合は、目的の指標とディメンションを表示するテーブルのビジュアライゼーションを作成します。
1. Right-click the top border of the callout window and click **[!UICONTROL Save]**.
1. In the [!DNL Save] window, click ![](assets/btn_folder_up.png), double-click **[!UICONTROL Context]**, then double-click **[!UICONTROL Callout]**. In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. 引き出し線ファイルは、User\*working profile name*\Context\Callout folderフォルダーに保存されます。

   >[!NOTE]
   >
   >引き出し線に名前を付ける場合は、ビジュアライゼーションのタイプと、表示される指標とディメンションを反映するわかりやすい名前を選択します。 例えば、Day（日）ディメンションに対する Sessions（セッション）指標を示すテーブルのビジュアライゼーションから引き出し線を作成する場合、その引き出し線に「Sessions by Day Table（日別のセッションテーブル）」という名前を付けられます。

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. で、をクリ [!DNL Profile Manager]ックし、を **[!UICONTROL Context]**&#x200B;クリックしま **[!UICONTROL Callout]**&#x200B;す。 This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types.

   1. Right-click the check mark next to the file name of the new callout in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**引き出し線を指標引き出し線に変更するには**

1. で、をクリ [!DNL Profile Manager]ックし、を **[!UICONTROL Context]**&#x200B;クリックしま **[!UICONTROL Callout]**&#x200B;す。 This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types.

1. Right-click the check mark next to the file name of the type of callout that you want to change and click **[!UICONTROL Make Local]**. ファイルがローカルコンピューターにダウンロードされると、[!DNL User] 列にチェックマークが表示されます。

1. Right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Locate the [!DNL metric_y = ref:] entry in the callout file and replace the existing value with the word Metric. 以下のファイルの一部でハイライトされているテキストは、Metric という語を挿入する場所を示しています。

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

1. クリック **[!UICONTROL File]** > **[!UICONTROL Save As]**. ウィンドウ **[!UICONTROL Save As]** で1回クリックし、ダブルクリックしま **[!UICONTROL Metric Callout]**&#x200B;す。 In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. 指標引き出し線ファイルは、User\*working profile name*\Context\Metric Callout folderフォルダーに保存されます。

1. (Optional) To make this metric callout available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

