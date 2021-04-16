---
description: ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。
title: 新しいベクターレイヤーを使用可能にする
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# 新しいベクターレイヤーを使用可能にする{#make-a-new-vector-layer-available}

ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。

1. Data Workbenchサーバーのインストールディレクトリ内のプロファイル\*プロファイル名*\Mapsフォルダーに、レイヤーファイルと[!DNL .vec]ファイルまたは[!DNL .tsv]ファイルを配置します。
1. プロファイル\*プロファイル名*\Mapsフォルダー内の[!DNL order.txt]ファイルを編集し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >[!DNL order.txt]ファイルを編集する際は、表示するマップレイヤーを隠さないように注意してください。

   [!DNL order.txt]ファイルの使用に関する詳細は、[Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)を参照してください。

1. Insightで、ワークスペースのタイトルバーを右クリックし、**[!UICONTROL Switch Profile]**/*&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、目的のプロファイルを選択します。
1. ワークスペースのタイトルバーを右クリックし、「**[!UICONTROL Work Online]**」をクリックします。 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
