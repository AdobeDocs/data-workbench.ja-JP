---
description: ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。
solution: Analytics
title: 新しいベクトルレイヤーを使用可能にする
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Make a new vector layer available{#make-a-new-vector-layer-available}

ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順。

1. In the Profiles\*profile name*\Maps folder within the Data Workbench server installation directory, place the layer file and the [!DNL .vec] or [!DNL .tsv] files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   ファイルの使用方法の詳細については、 [!DNL order.txt] 「Customizing Menus Using Order.txt Files [」を参照してください](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。

1. In Insight, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
