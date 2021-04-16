---
description: Webサーバーからイベントデータを収集する場合、Sensorは、個人識別情報を捕捉することなく、小さなランダムな識別子を含む各訪問者に永続的なcookieを自動的に設定します。
title: センサーによる訪問者やセッションの識別方法
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
exl-id: f5781ed6-ac83-4a8e-b412-8966f8c39c41
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 6%

---

# センサーによる訪問者やセッションの識別方法{#how-does-sensor-identify-visitors-and-sessions}

Webサーバーからイベントデータを収集する場合、Sensorは、個人識別情報を捕捉することなく、小さなランダムな識別子を含む各訪問者に永続的なcookieを自動的に設定します。

このAdobecookieは、個別訪問者とその関連するすべてのセッションを識別するために使用されます。

デフォルトでは、[!DNL Sensor]は各HTTPヘッダーからすべてのW3C拡張ログファイル形式フィールドを取り込みますが、クライアントとサーバーの間で送信されるヘッダーを取り込むように[!DNL Sensor]を設定できます。 [!DNL Sensor]によって[!DNL .vsl]ファイル内に収集されたイベントデータフィールドについて詳しくは、[イベントデータレコードフィールド](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)を参照してください。

一部の訪問者のブラウザーではcookieが永続的に保存されず、ごく少数の訪問者ーのブラウザーでcookieがまったく受け入れられない場合があります（セッションcookieも含む）。 サイトの総トラフィックのほんの一部を占めるに過ぎないにもかかわらず、一部のログファイル分析ソフトウェアが行うように、その訪問者による各ページ表示がセッション全体として誤ってカウントされる場合、大きな誤カウントが発生する可能性があります。 Adobeは、cookieの使用と使用を有効にして訪問者を分析できるようにすることで、この問題に対処します。

切断セッションフィルターの詳細については、『*Data Workbenchセンサーガイド*』を参照してください。
