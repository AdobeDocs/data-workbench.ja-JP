---
description: Siteの一般的な設定では、Webサイトへの訪問者を一意に識別し、時間の経過とともにその行動を追跡するためにcookieを使用します。
solution: Analytics,Analytics
title: サイトでの訪問者の識別方法
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# サイトでの訪問者の識別方法{#how-does-site-identify-visitors}

Siteの一般的な設定では、Webサイトへの訪問者を一意に識別し、時間の経過とともにその行動を追跡するためにcookieを使用します。

特定のブラウザー(訪問者と見なされる)がWebサイトを初めてリクエストすると、[!DNL Sensor]はWebサーバーと連携して持続的cookieを設定します（デフォルトでは[!DNL cs(cookie)(v1st)]）。これは、システム内では内部的に[!DNL x-trackingid]と解釈されます。 このcookieは、その訪問者が貴社のウェブサイトに対して行った最初のリクエスト時に1回だけ設定されます。 次に、ブラウザーがWebサイトに対して将来リクエスト（ページまたは埋め込みオブジェクトのリクエスト）を行うたびに、その訪問者から収集されます。

永続的なcookieを受け入れる場合は、ブラウザーの判断に従います。 永続的なcookieをブロックするように選択した場合、ページ表示リクエストはログに記録されますが、それらのリクエストからの測定データは、訪問者IDの代替訪問者（IPやUserAgentフィールドでのHash変換の使用など）を実装しない限り、Webサイト上の特定のセッションに関連付けられません。

>[!NOTE]
>
>サイトの実験は、[!DNL Sensor] set persistent cookieメソッドだけが使用される訪問者識別方式であるデータセットでのみ分析できます。 J2EEサーバー（JBoss、Tomcat、WebLogicおよびWebSphere）上で実行されるセンサーは、実験の制御をサポートしません。

対照実験では、cookieを受け入れないユーザーは、1回のクリックから次のクリックまで異なる実験グループに配置できます。 これは、[!DNL Insight]で切断セッションフィルターをオフにしてテスト分析を実行する場合にのみ問題となり、このAdobeは推奨されません。

切断セッションフィルターの詳細については、* [!DNL Insight]ユーザーガイド*を参照してください。

テスト中に訪問者がcookieをクリアした場合、訪問者に新しいcookieが割り当てられ、場合によっては別のグループに割り当てられます。 Adobeは、訪問者を新しいものと認識するので、テストは無効になりません。
