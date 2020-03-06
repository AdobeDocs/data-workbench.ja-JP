---
description: Webサーバーからイベントデータを収集する場合、Sensorは、個人を特定する情報を取り込まずに、小さなランダムな識別子を含む各訪問者の永続的なcookieを自動的に設定します。
solution: Insight
title: Sensorは訪問者やセッションをどのように識別しますか。
uuid: 3735ed2d-67c4-469b-8b3e-0fac90cc4c09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sensorは訪問者やセッションをどのように識別しますか。{#how-does-sensor-identify-visitors-and-sessions}

Webサーバーからイベントデータを収集する場合、Sensorは、個人を特定する情報を取り込まずに、小さなランダムな識別子を含む各訪問者の永続的なcookieを自動的に設定します。

このAdobe cookieは、個別訪問者とその関連するすべてのセッションを識別するために使用されます。

デフォルトでは、 [!DNL Sensor] は各HTTPヘッダーからすべてのW3C拡張ログファイル形式フィールドを取り込みますが、クライアントとサーバーの間で送信されるヘッダーを [!DNL Sensor] 取り込むように設定することもできます。 ファイルで収集されるイベントデータフィールドについて詳し [!DNL Sensor] くは、「イベ [!DNL .vsl] ントデータレコード [フィールド」を参照してくださ](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)い。

一部の訪問者のブラウザーではcookieが永続的に保存されず、ごく少数の訪問者のブラウザーではcookieがまったく受け入れられません（セッションcookieも含む）。 サイトの全トラフィックのごく一部を占めているにもかかわらず、一部のログファイル分析ソフトウェアのように、訪問者による各ページビューがセッション全体として誤ってカウントされると、大量の誤カウントが発生する可能性があります。 アドビでは、cookieを使用して訪問者を分析し、cookieを使用しないで訪問者を分析できるようにすることで、この問題に対処します。

壊れたセッションフィルターについて詳しくは、『 *Data Workbench Sensor Guide』を参照してください*。
