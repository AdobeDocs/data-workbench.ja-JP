---
description: 要素ポイントレイヤーを使用可能にして、グローブのビジュアライゼーション上に表示するための手順です。
title: 新しい要素ポイントレイヤーを使用可能にする
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 59%

---

# 新しい要素ポイントレイヤーを使用可能にする{#make-a-new-element-point-layer-available}

要素ポイントレイヤーを使用可能にして、グローブのビジュアライゼーション上に表示するための手順です。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとその関連する参照ファイルを配置します。
1. 要素ポイントレイヤーの新しいディメンションを定義し、まだデータセットを再変換していない場合は、ここでデータセットを再変換します。
1. Profiles\*profile name*\Mapsフォルダーの[!DNL order.txt]ファイルを編集して、レイヤーを表示する順序を反映します。 デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >[!DNL order.txt]ファイルを編集する際は、表示するマップレイヤを覆わないように注意してください。

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. Data Workbenchで、ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Switch Profile]** / *&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、目的のプロファイルを選択します。
1. ワークスペースのタイトルバーを右クリックし、「**[!UICONTROL Work Online]**」をクリックします。 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
