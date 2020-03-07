---
description: 要素ポイントレイヤーを使用可能にして、グローブのビジュアライゼーション上に表示するための手順です。
solution: Analytics
title: 新しい要素ポイントレイヤーを使用可能にする
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Make a new element point layer available{#make-a-new-element-point-layer-available}

要素ポイントレイヤーを使用可能にして、グローブのビジュアライゼーション上に表示するための手順です。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとその関連する参照ファイルを配置します。
1. 要素ポイントレイヤーの新しいディメンションを定義し、まだデータセットを再変換していない場合は、ここでデータセットを再変換します。
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. In Data Workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. 「オンラインで作業」の横に X マークが表示されます。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
