---
description: 地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新しい地形画像レイヤーを使用可能にする
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 54%

---

# 新しい地形画像レイヤーを使用可能にする{#make-a-new-terrain-image-layer-available}

{{eol}}

地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbenchサーバーのインストールディレクトリ内の Profiles\*profile name*\Maps フォルダーに、レイヤーファイルとサポート画像ファイルを配置します。
1. を編集します。 [!DNL order.txt] ファイルを Profiles\*profile name*\Maps フォルダーに保存し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >を編集する際に [!DNL order.txt] ファイルを表示するマップ画層を覆い隠さないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbenchで、ワークスペースのタイトルバーを右クリックし、「 」をクリックして、目的のプロファイルを選択します **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Work Online]**. 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
