---
description: レポートの生成時に電子メールを送信するようにData Workbenchを設定できます。
title: レポート完成時の電子メールによる通知
uuid: 567e0423-a17a-407c-87ea-735c1c8aef96
exl-id: 1d79fac9-667d-4139-8629-69c8795377b1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 11%

---

# レポート完成時の電子メールによる通知{#email-notification-of-completed-report}

レポートの生成時に電子メールを送信するようにData Workbenchを設定できます。

この値をTrueに設定すると、レポートが送信されず、購読ユーザーにレポートが生成されたことを知らせる電子メールが送信されます。

1. [!DNL Reports]メニューから「**[!UICONTROL Monthly]**」タブをクリックします。
1. [!DNL report.cfg]ファイルを開きます。
1. 「 [!DNL Notification Only] 」フィールドにtrueと入力し、レポートの完了時に電子メールを送信します。
