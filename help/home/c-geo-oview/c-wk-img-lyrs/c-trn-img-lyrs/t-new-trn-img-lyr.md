---
description: 新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新規地形画像レイヤーを利用可能にする
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 36%

---

# 新規地形画像レイヤーを利用可能にする{#making-a-new-terrain-image-layer-available}

新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. **[!UICONTROL Insight Server]**&#x200B;インストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとサポート画像ファイルを配置します。
1. Profiles\*profile name*\Mapsフォルダーの[!DNL order.txt]ファイルを編集して、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >[!DNL order.txt]ファイルを編集する際は、表示するマップレイヤを覆わないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbenchで、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** / *&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、目的のプロファイルを選択します。
1. ワークスペースのタイトルバーを右クリックし、「**[!UICONTROL Work Online]**」をクリックします。 [!DNL Work Online]の横にXが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
