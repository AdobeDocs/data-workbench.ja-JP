---
description: ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新しいベクターレイヤーを使用可能にする
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 35%

---

# 新しいベクターレイヤーを使用可能にする{#making-a-new-vector-layer-available}

{{eol}}

ベクトルレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbench サーバーのインストールディレクトリ内の Profiles\*profile name*\Maps フォルダーに、レイヤーファイルと [!DNL .vec] または [!DNL .tsv] ファイル。
1. を編集します。 [!DNL order.txt] ファイルを Profiles\*profile name*\Maps フォルダーに保存し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >を編集する際に [!DNL order.txt] ファイルを表示するマップ画層を覆い隠さないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbench で、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Work Online]**. の横に X が表示されます。 [!DNL Work Online].
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
