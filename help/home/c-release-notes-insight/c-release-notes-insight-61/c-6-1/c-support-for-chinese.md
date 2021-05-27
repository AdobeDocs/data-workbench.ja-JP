---
description: Data Workbench クライアントアプリケーションでは、現在、簡体字中国語をサポートしています。
title: 簡体字中国語のローカリゼーション
uuid: ddf4eade-7c5f-4ccf-aa9f-dd8d109a059f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 100%

---


# 簡体字中国語のローカリゼーション{#simplified-chinese-localization}

Data Workbench クライアントアプリケーションでは、現在、簡体字中国語をサポートしています。

**簡体字中国語をインストールするには**：

[!DNL Insight.exe] およびサポートファイルを設定する前に、クライアントアプリケーションを終了する必要があります。

1. コマンドライン設定で [!DNL insight.exe] ファイルに渡すショートカットを作成します。

   ```
   Insight.exe -zh-cn
   ```

1. 半角および全角フォント文字をサポートするように [!DNL Insight.cfg] を設定します。

   Data Workbench では、現在、英語と簡体字中国語の両方をサポートしています。これら両方の言語をサポートするフォントを選択できます。

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. 再起動 [!DNL Insight.exe].

