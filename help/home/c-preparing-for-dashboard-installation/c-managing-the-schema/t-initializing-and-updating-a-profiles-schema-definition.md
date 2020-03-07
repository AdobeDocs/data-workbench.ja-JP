---
description: 'null'
solution: Analytics
title: プロファイルのスキーマ定義の初期化と更新
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# プロファイルのスキーマ定義の初期化と更新{#initializing-and-updating-a-profile-s-schema-definition}

1. 設定する **[!UICONTROL Schema Builder]** プロファイルのを開きます。
1. スキー **[!UICONTROL Loading]** マがInsightプロファイルから取得される間、メッセージが表示されます。 スキーマの読み込みに要する時間は、読み込まれるプロファイルの複雑さによって異なります。
1. 完了すると、左側のペインと右側のペインの **[!UICONTROL Insight Schema]** 違いの概要が表 **[!UICONTROL Dashboard Schema]** 示されます。 この概要は、ウィンドウの左下部に表示され **[!UICONTROL Schema Builder]** ます。

   >[!NOTE]
   >
   >初めてスキーマを設定する場合、各指標、ディメンションおよびフィルターは、ダッシュボードのスキーマとは異なる方法で表示されます。 これは、現時点ではダッシュボードスキーマオブジェクトが存在しないためです。

   ![](assets/schema_builder2.png)

1. ボタンをクリック **[!UICONTROL Synchronize with Schema]** して、Insight Schemaビューのすべての指標、ディメンションおよびフィルターをダッシュボードスキーマビューと同期します。
1. 完了すると、違いが見つからないことを示すメッセージが表示されます。

   ![](assets/diff_found.png)

1. ダッシュボードスキーマに重複した指標やディメンションなどのエラーがある場合は、保存する前に手動で修正する必要があります。

   >[!NOTE]
   >
   >ダッシュボードのエンドユーザーに表示しない指標、ディメンシ **[!UICONTROL Dashboard Schema]** ョンまたはフィルターを、選択して削除することができます。 項目がダッシュボードスキーマに存在しないという警告が表示されますが、保存を妨げることはありません。

1. 準備が整ったら、をクリ **[!UICONTROL Save]** ックして、変更内容をダッシュボードのスキーマに保存します。
1. ダッシュボードシステムは、このスキーマ定義を使用して、ダッシュボードインターフェイスのエンドユーザーが使用できるディメンション、指標およびフィルターを設定します。
