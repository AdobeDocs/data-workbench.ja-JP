---
description: ユーザーの認証に必要な情報を含むデータベースに Report Portal が書き込めるようにするには、データベースに対して適切な権限を設定する必要があります。
title: データベースの権限の設定
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# データベースの権限の設定{#set-permissions-for-the-database}

{{eol}}

ユーザーの認証に必要な情報を含むデータベースに Report Portal が書き込めるようにするには、データベースに対して適切な権限を設定する必要があります。

1. IIS が実行されているマシンで、\*PortalName*\data\users.mdb に移動します。
1. を右クリックします。 **[!UICONTROL users.mdb]** ファイルと選択 **[!UICONTROL Properties]**.
1. の [!DNL Security] タブで、グループまたはユーザー名の **[!UICONTROL Users]**.
1. In [!DNL Permission for User]、「Write」行で、「 **[!UICONTROL Allow]**.
1. クリック **[!UICONTROL OK]** をクリックし、 [!DNL Properties] ダイアログボックス
