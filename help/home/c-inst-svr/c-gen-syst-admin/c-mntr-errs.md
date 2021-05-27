---
description: システムエラーとアプリケーションエラーを可能な限り早く検出し、重大な問題や停止を引き起こす前に対処するには、イベントログを定期的に監視する必要があります。
title: エラーのイベントの監視
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
exl-id: 88f48594-5c73-4ae3-8014-b8543e689426
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 5%

---

# エラーのイベントの監視{#monitoring-events-for-errors}

システムエラーとアプリケーションエラーを可能な限り早く検出し、重大な問題や停止を引き起こす前に対処するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 5 ～ 10分ごと

Adobe・サーバ・ソフトウェア製品を監視するために、自動管理ツールを設定して、ソース「Adobe」に関するエラーをイベントログに監視し、介入が必要な問題に対して適切な担当者に警告を出すことができます。

Windowsでは、アプリケーションエラーメッセージは、Windowsの「アプリケーションイベントログ」に出力され、Windowsのイベントビューアを使用してアクセスできます。 UNIXでは、LOG_DAEMON機能を使用して、アプリケーションエラーメッセージがUnix syslogに出力されます。

**Windowsイベントビューアを開くには**

* **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**&#x200B;をクリックします。
