---
description: 相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。
title: 相関行列のバイナリフィルター
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 55%

---

# 相関行列のバイナリフィルター{#binary-filter-in-the-correlation-matrix}

{{eol}}

相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。

相関行列にバイナリフィルターを設定するには：

1. 相関行列から、指標名を右クリックします。
1. 「**相関の詳細を編集**」を選択します。

   ![](assets/correlation_matrix_binary_filter.png)

   この **[!UICONTROL Edit Correlation Metric Details]** ウィンドウが開きます。

   ![](assets/correlation_matrix_metric_details.png)

1. バイナリフィルターを設定します。

   まず、 **[!UICONTROL Inactive]** 設定。 フィルターを次のように設定する切り替えが行われます。 **[!UICONTROL Active]** と **比較** および **値** フィールド。

   次に、 **[!UICONTROL Comparison]** 演算子と **[!UICONTROL Value]** 選択した指標のフィルターを設定します。

>[!IMPORTANT]
>
>Data Workbench6.2 のバイナリフィルターが更新され、新しい機能が追加されました。以前のバージョンで作成されたバイナリフィルターを使用して相関行列を再構築する必要があります。

## ディメンションエレメントの追加 {#section-f19f4e0368ca488e92d1e28bcc24417c}

ディメンションエレメントを追加して、指標を制限することもできます。指標には、エレメントを 1 つだけ関連付けることができます。

![](assets/correlation_matrix_element.png)

ワークスペース内で右クリックして、「**テーブル**」を選択します。 要素を含むディメンションを開き、 **[!UICONTROL Element]** 設定を使用するか、相関行列の指標にドロップします。
