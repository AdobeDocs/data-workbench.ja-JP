---
description: システムエラーとアプリケーションエラーをできるだけ早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。
title: エラーのイベントの監視
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---

# エラーのイベントの監視{#monitoring-events-for-errors}

システムエラーとアプリケーションエラーをできるだけ早く検出し、重大な問題や障害が発生する前に対処するには、イベントログを定期的に監視する必要があります。

**推奨頻度：5 ～ 10分** ごと

Adobe・サーバ・ソフトウェア製品を監視するために、自動管理ツールを設定して、イベント・ログのソース「Adobe」に関するエラーを監視し、介入が必要な問題を適切な担当者に通知できます。

Windowsでは、アプリケーションエラーメッセージはWindowsの「アプリケーションイベントログ」に出力され、WindowsイベントViewerからアクセスできます。 UNIXでは、LOG_DAEMON機能を使用して、アプリケーションエラーメッセージがUnixのsyslogに出力されます。

**Windowsイベントビューアを開くには**

* **[!UICONTROL Start]**/**[!UICONTROL Control Panel]**/**[!UICONTROL Administrative Tools]**/**[!UICONTROL Event Viewer]**&#x200B;をクリックします。
