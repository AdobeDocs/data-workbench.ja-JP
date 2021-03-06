---
description: 要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
title: 新しい要素ポイントレイヤーを使用可能にする
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 42%

---

# 新しい要素ポイントレイヤーを使用可能にする{#making-a-new-element-point-layer-available}

要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとその関連する参照ファイルを配置します。
1. 要素ポイントレイヤーの新しいディメンションを定義し、まだデータセットを再変換していない場合は、ここでデータセットを再変換します。
1. Profiles\*profile name*\Mapsフォルダーの[!DNL order.txt]ファイルを編集して、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >[!DNL order.txt]ファイルを編集する際は、表示するマップレイヤを覆わないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbenchで、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** / *&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、目的のプロファイルを選択します。
1. ワークスペースのタイトルバーを右クリックし、「**[!UICONTROL Work Online]**」をクリックします。 [!DNL Work Online]の横にXが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
