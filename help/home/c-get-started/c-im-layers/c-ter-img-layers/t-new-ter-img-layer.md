---
description: 地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新しい地形画像レイヤーを使用可能にする
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 54%

---

# 新しい地形画像レイヤーを使用可能にする{#make-a-new-terrain-image-layer-available}

地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Profiles\*profile name*\Mapsフォルダー内のProfilesサーバーのData Workbenchディレクトリに、レイヤーファイルとサポートする画像ファイルを配置します。
1. Profiles\*profile name*\Mapsフォルダーの[!DNL order.txt]ファイルを編集して、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >[!DNL order.txt]ファイルを編集する際は、表示するマップレイヤを覆わないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbenchで、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** / *&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、目的のプロファイルを選択します。
1. ワークスペースのタイトルバーを右クリックし、「**[!UICONTROL Work Online]**」をクリックします。 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
