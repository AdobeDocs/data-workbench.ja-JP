---
description: レポートポータルで、ユーザーの認証に必要な情報を含むデータベースに書き込むための設定を有効にするには、データベースに対して適切な権限を設定する必要があります。
solution: Analytics
title: データベースの権限の設定
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データベースの権限の設定{#set-permissions-for-the-database}

レポートポータルで、ユーザーの認証に必要な情報を含むデータベースに書き込むための設定を有効にするには、データベースに対して適切な権限を設定する必要があります。

1. IISを実行しているマシンで、\*PortalName*\data\users.mdbに移動します。
1. ファイルを右クリックし **[!UICONTROL users.mdb]** て、を選択しま **[!UICONTROL Properties]**&#x200B;す。
1. タブの「グ [!DNL Security] ループまたはユーザー名」で、をクリックしま **[!UICONTROL Users]**&#x200B;す。
1. の[書 [!DNL Permission for User]き込み]行で、を選択しま **[!UICONTROL Allow]**&#x200B;す。
1. をクリック **[!UICONTROL OK]** して、ダイアログボッ [!DNL Properties] クスを閉じます。
