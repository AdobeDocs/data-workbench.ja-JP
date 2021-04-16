---
description: 相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。
title: 相関行列のバイナリフィルター
uuid: 61c3ca37-cfa2-49dc-87de-4e9a44647eca
exl-id: e693fc72-5697-4c47-a498-e0d4d875c688
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 55%

---

# 相関行列のバイナリフィルター{#binary-filter-in-the-correlation-matrix}

相関行列でバイナリフィルターを使用すると、相関している指標のどちらかまたは両方の値を制限して、比較対象を絞り込むことができます。

相関行列にバイナリフィルターを設定するには：

1. 相関行列から、指標名を右クリックします。
1. 「**相関の詳細を編集**」を選択します。

   ![](assets/correlation_matrix_binary_filter.png)

   **[!UICONTROL Edit Correlation Metric Details]**&#x200B;ウィンドウが開きます。

   ![](assets/correlation_matrix_metric_details.png)

1. バイナリフィルターを設定します。

   最初に、**[!UICONTROL Inactive]**&#x200B;設定をクリックします。 フィルターを&#x200B;**[!UICONTROL Active]**&#x200B;に設定し、**比較**&#x200B;フィールドと&#x200B;**値**&#x200B;フィールドを表示するように切り替えます。

   次に、**[!UICONTROL Comparison]**&#x200B;演算子を選択し、**[!UICONTROL Value]**&#x200B;を設定して、選択した指標のフィルターを設定します。

>[!IMPORTANT]
>
>Data Workbench6.2のバイナリフィルターは更新され、新機能が追加されました。そのため、以前のバージョンで作成したバイナリフィルターを使用した相関行列はすべて作成し直す必要があります。

## ディメンションエレメントの追加 {#section-f19f4e0368ca488e92d1e28bcc24417c}

ディメンションエレメントを追加して、指標を制限することもできます。指標には、エレメントを 1 つだけ関連付けることができます。

![](assets/correlation_matrix_element.png)

ワークスペース内で右クリックして、「**テーブル**」を選択します。 エレメントを含むディメンションを開き、相関指標の詳細を編集ウィンドウの&#x200B;**[!UICONTROL Element]**&#x200B;設定にドラッグするか、相関行列の指標にドロップします。
