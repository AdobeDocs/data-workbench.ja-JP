---
description: 相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。
solution: Analytics
title: 相関行列のバイナリフィルター
topic: Data workbench
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 相関行列のバイナリフィルター{#binary-filter-in-the-correlation-matrix}

相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。

相関行列にバイナリフィルターを設定するには：

1. 相関行列から、指標名を右クリックします。
1. 「**相関の詳細を編集**」を選択します。

   ![](assets/correlation_matrix_binary_filter.png)

   窓が **[!UICONTROL Edit Correlation Metric Details]** 開きます。

   ![](assets/correlation_matrix_metric_details.png)

1. バイナリフィルターを設定します。

   First, click the **[!UICONTROL Inactive]** setting. It will toggle to set the filter as **[!UICONTROL Active]** and display the **Comparison** and **Value** fields.

   Then, select a **[!UICONTROL Comparison]** operator and set its **[!UICONTROL Value]** to set up a filter for the selected metric.

>[!IMPORTANT]
>
>Data Workbench 6.2のバイナリフィルターが更新され、新機能が追加されました。そのため、以前のバージョンで作成されたバイナリフィルターを使用して相関行列を作成し直す必要があります。

## ディメンションエレメントの追加 {#section-f19f4e0368ca488e92d1e28bcc24417c}

ディメンションエレメントを追加して、指標を制限することもできます。指標には、エレメントを 1 つだけ関連付けることができます。

![](assets/correlation_matrix_element.png)

ワークスペース内で右クリックして、「**テーブル**」を選択します。 Open a dimension with its elements and drag to the **[!UICONTROL Element]** setting in the Edit Correlation Metric Details window, or drop on a metric in the Correlation Matrix.
