---
description: システムエラーとアプリケーションエラーを可能な限り早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。
solution: Insight
title: エラーのイベントの監視
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# エラーのイベントの監視{#monitoring-events-for-errors}

システムエラーとアプリケーションエラーを可能な限り早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 5 ～ 10分ごと

アドビのサーバーソフトウェア製品を監視するために、自動管理ツールを設定して、「アドビ」のソースに関するエラーのイベントログを監視し、介入が必要な問題に適切な担当者に警告することができます。

Windowsの場合、アプリケーションエラーメッセージはWindowsのアプリケーションイベントログに出力され、Windowsのイベントビューアを使用してアクセスできます。 UNIXでは、LOG_DAEMON機能を使用して、アプリケーションのエラー・メッセージがUnixのsyslogに出力されます。

**Windowsイベントビューアを開くには**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

