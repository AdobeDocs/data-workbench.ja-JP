---
description: 新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新規地形画像レイヤーを利用可能にする
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 36%

---

# 新規地形画像レイヤーを利用可能にする{#making-a-new-terrain-image-layer-available}

{{eol}}

新しい地形レイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. 次の場所にある Profiles\*profile name*\Maps フォルダー： **[!UICONTROL Insight Server]** インストールディレクトリに、レイヤーファイルとサポート画像ファイルを配置します。
1. を編集します。 [!DNL order.txt] ファイルを Profiles\*profile name*\Maps フォルダーに保存し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >を編集する際に [!DNL order.txt] ファイルを表示するマップ画層を覆い隠さないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbench で、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Work Online]**. の横に X が表示されます。 [!DNL Work Online].
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
