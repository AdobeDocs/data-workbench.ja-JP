---
description: 新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
solution: Analytics
title: 新規地形画像レイヤーを利用可能にする
topic: Data workbench
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新規地形画像レイヤーを利用可能にする{#making-a-new-terrain-image-layer-available}

新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. In the Profiles\*profile name*\Maps folder within the **[!UICONTROL Insight Server]** installation directory, place the layer file and the supporting image files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. の横にXが表示されま [!DNL Work Online]す。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
