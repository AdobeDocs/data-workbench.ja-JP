---
description: 重大な問題や停止を引き起こす前に、システムやアプリケーションのエラーをできるだけ早く検出して対処するには、イベントログを定期的に監視する必要があります。
title: エラーのイベントの監視
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---

# エラーのイベントの監視{#monitoring-events-for-errors}

{{eol}}

重大な問題や停止を引き起こす前に、システムやアプリケーションのエラーをできるだけ早く検出して対処するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 5 ～ 10 分ごと

Adobe・サーバ・ソフトウェア製品を監視するには、自動管理ツールを設定して、イベント・ログを監視してソースの「Adobe」に関するエラーを検出し、介入が必要な問題に対して適切な担当者に警告を出します。

Windows では、アプリケーションエラーメッセージは、Windows の [ アプリケーションイベントログ ] に出力され、Windows のイベントビューアを使用してアクセスできます。 UNIX では、LOG_DAEMON 機能を使用して、アプリケーションのエラーメッセージが Unix の syslog に出力されます。

**Windows イベントビューアを開くには**

* クリック **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.
