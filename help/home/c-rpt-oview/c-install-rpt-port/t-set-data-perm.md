---
description: ユーザーの認証に必要な情報を含むデータベースにReport Portalが書き込めるようにするには、データベースに対する適切な権限を設定する必要があります。
title: データベースの権限の設定
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# データベースの権限の設定{#set-permissions-for-the-database}

ユーザーの認証に必要な情報を含むデータベースにReport Portalが書き込めるようにするには、データベースに対する適切な権限を設定する必要があります。

1. IISが実行されているマシンで、\*PortalName*\data\users.mdbに移動します。
1. **[!UICONTROL users.mdb]**&#x200B;ファイルを右クリックし、**[!UICONTROL Properties]**&#x200B;を選択します。
1. 「[!DNL Security]」タブの「グループ」または「ユーザー名」で、「**[!UICONTROL Users]**」をクリックします。
1. [!DNL Permission for User]の[書き込み]行で、**[!UICONTROL Allow]**&#x200B;を選択します。
1. **[!UICONTROL OK]**&#x200B;をクリックし、[!DNL Properties]ダイアログボックスを閉じます。
