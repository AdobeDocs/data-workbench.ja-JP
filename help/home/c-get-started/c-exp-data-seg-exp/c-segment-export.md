---
description: セグメントエクスポートファイルのカスタム列のエクスポートヘッダーを作成して、エクスポートされたセグメントのわかりやすい説明を追加できます。このエクスポート機能を使用して、TSV や CSV ファイルとして出力することもできます。
title: カスタムヘッダーでのセグメントエクスポート
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 59%

---

# カスタムヘッダーでのセグメントエクスポート{#segment-export-with-custom-headers}

{{eol}}

セグメントエクスポートファイルのカスタム列のエクスポートヘッダーを作成して、エクスポートされたセグメントのわかりやすい説明を追加できます。このエクスポート機能を使用して、TSV や CSV ファイルとして出力することもできます。

ヘッダー付きや CSV および TSV 形式でエクスポートする機能などの新機能がセグメントエクスポートに追加されました。

エクスポートファイルの列ヘッダーを作成できます。

## 新しいセグメントエクスポートの作成 {#section-cffff55855f8467ea468b71393ab7676}

1. ワークスペースを開いて右クリック **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. 右クリックして「 」を選択します。 **[!UICONTROL Add Level > Extended]** > 項目を選択します。
1. タイトルを右クリックし、「 」を選択します。 **[!UICONTROL Add Attribute.]** メニューから寸法を選択します。

1. タイトルを右クリックし、「 」を選択します。 **[!UICONTROL Add Metric.]** メニューから指標を選択します。

1. タイトルを右クリックし、「 」を選択します。 **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** は、指標の名前で列名を自動的に入力します。 **[!UICONTROL New Segment Export]** では、カスタム名を設定する必要があります。 ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >「列名」フィールドを空白にすることはできません。空白にすると、ヘッダーが存在しなくなります。

1. 右クリックしてセグメントに名前を付け、「 」をクリックします。 **[!UICONTROL Save Export File]**.

   エクスポートウィンドウが開きます。

1. エクスポート名を右クリックし、 **名前を付けて保存`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. 右クリック [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. 作成したエクスポートファイルを見つけ、既存のプロファイルに保存します。

   ![](assets/segment_export_headers_8.png)
