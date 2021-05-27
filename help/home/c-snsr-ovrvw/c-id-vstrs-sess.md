---
description: Webサーバーからイベントデータを収集する場合、Sensorは、個人識別情報を取り込むことなく、小さなランダム識別子を含む各訪問者の永続的なCookieを自動的に設定します。
title: センサーによる訪問者やセッションの識別方法
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# センサーによる訪問者やセッションの識別方法{#how-does-sensor-identify-visitors-and-sessions}

Webサーバーからイベントデータを収集する場合、Sensorは、個人識別情報を取り込むことなく、小さなランダム識別子を含む各訪問者の永続的なCookieを自動的に設定します。

このAdobeCookieは、個別訪問者とその関連するすべてのセッションを識別するために使用されます。

デフォルトでは、[!DNL Sensor]は各HTTPヘッダーからすべてのW3C拡張ログファイル形式フィールドを取り込みますが、クライアントとサーバーの間で送信されるヘッダーを取り込むように[!DNL Sensor]を設定できます。 [!DNL Sensor]によって[!DNL .vsl]ファイルで収集されるイベントデータフィールドについて詳しくは、[イベントデータレコードフィールド](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)を参照してください。

一部の訪問者のブラウザーではcookieが永続的に保存されず、非常に少数の訪問者のブラウザーではcookieがまったく受け入れられません（セッションcookieも含む）。 サイトの合計トラフィックのごく一部に過ぎませんが、一部のログファイル分析ソフトウェアがおこなうように、訪問者による各ページビューがセッション全体として正しくカウントされない場合、大量の誤カウントが発生する可能性があります。 Adobeは、Cookieを使用している場合と使用していない場合でも訪問者を分析できるので、この問題に対処します。

Broken Sessions Filterの詳細については、『*Data Workbenchセンサーガイド*』を参照してください。
