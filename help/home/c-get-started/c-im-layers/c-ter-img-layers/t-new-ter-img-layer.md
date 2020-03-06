---
description: 地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
solution: Analytics
title: 新しい地形画像レイヤーを使用可能にする
topic: Data workbench
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Make a new terrain image layer available{#make-a-new-terrain-image-layer-available}

地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとサポートする画像ファイルを配置します。
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. In Data Workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
