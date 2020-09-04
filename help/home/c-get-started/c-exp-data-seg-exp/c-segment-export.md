---
description: セグメントエクスポートファイルのカスタム列のエクスポートヘッダーを作成して、エクスポートされたセグメントのわかりやすい説明を追加できます。このエクスポート機能を使用して、TSV や CSV ファイルとして出力することもできます。
title: カスタムヘッダーでのセグメントエクスポート
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 89%

---


# カスタムヘッダーでのセグメントエクスポート{#segment-export-with-custom-headers}

セグメントエクスポートファイルのカスタム列のエクスポートヘッダーを作成して、エクスポートされたセグメントのわかりやすい説明を追加できます。このエクスポート機能を使用して、TSV や CSV ファイルとして出力することもできます。

ヘッダー付きや CSV および TSV 形式でエクスポートする機能などの新機能がセグメントエクスポートに追加されました。

エクスポートファイルの列ヘッダーを作成できます。

## 新しいセグメントエクスポートの作成 {#section-cffff55855f8467ea468b71393ab7676}

1. ワークスペースを開き、**[!UICONTROL ツール]**／**[!UICONTROL 詳細テーブル]**&#x200B;を右クリックします。

1. 右クリックして、**[!UICONTROL レベルを追加／拡張]**&#x200B;で項目を選択します。
1. タイトルを右クリックし、「**[!UICONTROL 属性を追加」を選択します。]**&#x200B;メニューからディメンションを選択します。

1. タイトルを右クリックし、「**[!UICONTROL 指標を追加」を選択します。]**&#x200B;メニューから指標を選択します。

1. タイトルを右クリックし、「**[!UICONTROL 新しいセグメントエクスポート]**」を選択します。

   ![](assets/segment_export_headers.png)

   「**[!UICONTROL 新しいセグメントのヘッダー付きエクスポート]**」を選択すると、指標の名前で Column Name が自動的に生成されます。「**[!UICONTROL 新しいセグメントエクスポート]**」を選択すると、カスタムの名前を設定する必要があります。 ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >[列名]フィールドを空のままにすることはできません。空のままにすると、ヘッダーが存在しなくなります。

1. 右クリックし、セグメントに名前をつけて「**[!UICONTROL エクスポートファイルを保存]**」をクリックします。

   エクスポートウィンドウが開きます。

1. Right-click the export name and click **Save as`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. Right-click [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. 作成したエクスポートファイルを見つけ、既存のプロファイルに保存します。

   ![](assets/segment_export_headers_8.png)

