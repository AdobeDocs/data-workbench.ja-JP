---
description: ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。
title: 新しいベクターレイヤーを使用可能にする
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 45%

---

# 新しいベクターレイヤーを使用可能にする{#make-a-new-vector-layer-available}

{{eol}}

ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。

1. Profiles\*profile name*\MapsData Workbenchーのインストールディレクトリに、レイヤーファイルと [!DNL .vec] または [!DNL .tsv] ファイル。
1. を編集します。 [!DNL order.txt] ファイルを Profiles\*profile name*\Maps フォルダーに保存し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >を編集する際に [!DNL order.txt] ファイルを表示するマップ画層を覆い隠さないように注意してください。

   詳しくは、 [!DNL order.txt] ファイル： [Order.txt ファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. Insight で、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Work Online]**. 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
