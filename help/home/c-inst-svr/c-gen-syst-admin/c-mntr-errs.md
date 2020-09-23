---
description: システムエラーとアプリケーションエラーをできるだけ早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。
solution: Analytics
title: エラーのイベントの監視
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---


# エラーのイベントの監視{#monitoring-events-for-errors}

システムエラーとアプリケーションエラーをできるだけ早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 5 ～ 10分ごと

Adobe・サーバ・ソフトウェア製品を監視するために、自動管理ツールを設定して、イベント・ログのソース「Adobe」に関するエラーを監視し、介入が必要な問題を適切な担当者に通知できます。

Windowsでは、アプリケーションエラーメッセージはWindowsの「アプリケーションイベントログ」に出力され、WindowsのイベントViewerからアクセスできます。 UNIXでは、LOG_DAEMON機能を使用して、アプリケーションエラーメッセージがUnixのsyslogに出力されます。

**Windowsイベントビューアを開くには**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

