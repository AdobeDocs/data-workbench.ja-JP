---
description: Siteの一般的な設定では、Webサイトへの訪問者を一意に識別し、その行動を経時的に追跡するためにcookieを使用します。
solution: Analytics,Analytics
title: サイトでの訪問者の識別方法
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# サイトでの訪問者の識別方法{#how-does-site-identify-visitors}

Siteの一般的な設定では、Webサイトへの訪問者を一意に識別し、その行動を経時的に追跡するためにcookieを使用します。

特定のブラウザー（訪問者と見なされる）がWebサイトで初めてリクエストをおこなう際、[!DNL Sensor]はWebサーバーと連携して永続的なcookieを設定します（デフォルトでは[!DNL cs(cookie)(v1st)]）。これはシステム内部で[!DNL x-trackingid]と解釈されます。 このcookieは、その訪問者がWebサイトに対して最初にリクエストしたときに1回だけ設定されます。 その後、ブラウザーが将来Webサイトのリクエスト（ページまたは埋め込みオブジェクトのリクエスト）をおこなうたびに、その訪問者から収集されます。

永続的なcookieを受け入れるかどうかは、ブラウザーの判断に従います。 永続的なcookieのブロックを選択した場合でも、ページビューリクエストは記録されますが、IPやUserAgentフィールドでのHash変換の使用など、訪問者を識別する別の方法を実装しない限り、Webサイト上の特定の訪問者やセッションに計測データが関連付けられません。

>[!NOTE]
>
>サイト実験は、[!DNL Sensor]設定された永続的なcookieメソッドのみが使用されるデータセットでのみ分析できます。 J2EEサーバー（JBoss、Tomcat、WebLogicおよびWebSphere）上で動作するセンサーは、対照実験をサポートしていません。

対照実験の間、cookieを受け入れないユーザーは、1回のクリックから次のクリックまで、異なる実験グループに配置できます。 これは、[!DNL Insight]でBroken Session Filterをオフにしてテスト分析を実行する場合にのみ発生し、Adobeは推奨されません。

Broken Session Filterの詳細については、『ユーザガイド』を参照してください。[!DNL Insight]

実験中に訪問者がcookieをクリアした場合、訪問者に新しいcookieが割り当てられ、別のグループに割り当てられる可能性があります。 Adobeは訪問者を新規と識別するので、実験は無効にはなりません。
