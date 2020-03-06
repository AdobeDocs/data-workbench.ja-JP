---
description: 要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。
solution: Analytics
title: 新規要素ポイントレイヤーを利用可能にする
topic: Data workbench
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新規要素ポイントレイヤーを利用可能にする{#making-a-new-element-point-layer-available}

要素ポイントレイヤーをグローブビジュアライゼーションに表示できるようにする手順です。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*profile name*\Mapsフォルダーに、レイヤーファイルとその関連する参照ファイルを配置します。
1. 要素ポイントレイヤーの新しいディメンションを定義し、まだデータセットを再変換していない場合は、ここでデータセットを再変換します。
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. デフォルトで、レイヤーは名前の辞書順で表示されます。

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   [!DNL order.txt] ファイルの使用方法の詳細については、『*Data Workbench ユーザーガイド*』のインターフェイスおよび分析機能の設定の章を参照してください。

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. の横にXが表示されま [!DNL Work Online]す。
1. ワークスペースを開き、グローブビジュアライゼーションで右クリックして、新しいレイヤーを選択します。レイヤー名の横に X マークが表示されます。
