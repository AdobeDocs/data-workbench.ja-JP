---
description: 要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新しい要素ポイントレイヤーを使用可能にする
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 42%

---

# 新しい要素ポイントレイヤーを使用可能にする{#making-a-new-element-point-layer-available}

{{eol}}

要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbench サーバーのインストールディレクトリ内の Profiles\*profile name*\Maps フォルダーに、レイヤーファイルとその関連する参照ファイルを配置します。
1. 要素ポイントレイヤーの新しいディメンションを定義し、まだデータセットを再変換していない場合は、ここでデータセットを再変換します。
1. を編集します。 [!DNL order.txt] ファイルを Profiles\*profile name*\Maps フォルダーに保存し、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >を編集する際に [!DNL order.txt] ファイルを表示するマップ画層を覆い隠さないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbench で、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Work Online]**. の横に X が表示されます。 [!DNL Work Online].
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
