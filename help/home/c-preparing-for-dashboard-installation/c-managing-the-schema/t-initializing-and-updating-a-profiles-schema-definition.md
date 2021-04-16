---
description: プロファイルのスキーマ定義の初期化と更新
title: プロファイルのスキーマ定義の初期化と更新
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# プロファイルのスキーマ定義の初期化と更新{#initializing-and-updating-a-profile-s-schema-definition}

1. 設定するプロファイルの&#x200B;**[!UICONTROL Schema Builder]**&#x200B;を開きます。
1. スキーマがInsightプロファイルから取得されている間は、**[!UICONTROL Loading]**&#x200B;メッセージが表示されます。 スキーマの読み込みに要する時間は、読み込まれるプロファイルの複雑さによって異なります。
1. 完了すると、左側のペインに&#x200B;**[!UICONTROL Insight Schema]**、右側のペインに&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;の違いの概要が表示されます。 この概要は、**[!UICONTROL Schema Builder]**&#x200B;ウィンドウの左下に表示されます。

   >[!NOTE]
   >
   >初めてスキーマを設定する場合、各指標、ディメンションおよびフィルターのリストは、ダッシュボードのスキーマとは異なります。 これは、ダッシュボードスキーマオブジェクトが現在存在しないためです。

   ![](assets/schema_builder2.png)

1. **[!UICONTROL Synchronize with Schema]**&#x200B;ボタンをクリックして、Insightスキーマ表示ーのすべての指標、ディメンションおよびフィルターをダッシュボードスキーマ表示と同期します。
1. 完了すると、違いが見つからないことを示すメッセージが表示されます。

   ![](assets/diff_found.png)

1. 重複指標やディメンションなど、ダッシュボードスキーマにエラーがある場合は、保存する前に手動で修正する必要があります。

   >[!NOTE]
   >
   >**[!UICONTROL Dashboard Schema]**&#x200B;から、ダッシュボードのエンドユーザーに表示したくない指標、ディメンションまたはフィルターを選択して削除できます。 アイテムがダッシュボードスキーマに存在しないという警告が表示されますが、保存を妨げることはありません。

1. 準備が整ったら、**[!UICONTROL Save]**&#x200B;をクリックして、変更をダッシュボードのスキーマに保存します。
1. ダッシュボードシステムは、このスキーマ定義を使用して、ダッシュボードインターフェイスのエンドユーザーが使用できるディメンション、指標およびフィルターを設定します。
