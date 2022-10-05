---
description: Web サーバーからイベントデータを収集する場合、Sensor は、個人識別情報を取り込まずに、小さなランダム識別子を含む永続的な cookie を各訪問者に対して自動的に設定します。
title: センサーによる訪問者やセッションの識別方法
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# センサーによる訪問者やセッションの識別方法{#how-does-sensor-identify-visitors-and-sessions}

{{eol}}

Web サーバーからイベントデータを収集する場合、Sensor は、個人識別情報を取り込まずに、小さなランダム識別子を含む永続的な cookie を各訪問者に対して自動的に設定します。

このAdobeCookie は、個別訪問者とその関連するすべてのセッションを識別するために使用されます。

デフォルトでは、 [!DNL Sensor] は、各 HTTP ヘッダーからすべての W3C 拡張ログファイル形式フィールドをキャプチャしますが、設定は可能です [!DNL Sensor] クライアントとサーバの間で送信されるヘッダを取り込む。 収集されるイベントデータフィールドの詳細 [!DNL Sensor] in [!DNL .vsl] ファイル： [イベントデータレコードフィールド](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

一部の訪問者のブラウザーでは cookie が永続的に保存されず、ごく少数の訪問者のブラウザーでは cookie を受け入れません（セッション cookie も含む）。 サイトの総トラフィックのごく一部に過ぎませんが、一部のログファイル分析ソフトウェアがおこなうように、訪問者が各ページを正しくセッション全体としてカウントしない場合は、大量の誤カウントが発生する可能性があります。 Adobeは、Cookie を使用して訪問者を分析し、使用しない訪問者を分析することで、この問題に対処します。

Broken Sessions フィルタの詳細については、 *Data Workbenchセンサーガイド*.
