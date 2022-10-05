---
description: Site の一般的な設定では、Web サイトへの訪問者を一意に識別し、訪問者の行動を経時的に追跡する目的で cookie を使用します。
solution: Analytics
title: サイトでの訪問者の識別方法
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# サイトでの訪問者の識別方法{#how-does-site-identify-visitors}

{{eol}}

Site の一般的な設定では、Web サイトへの訪問者を一意に識別し、訪問者の行動を経時的に追跡する目的で cookie を使用します。

特定のブラウザー（訪問者と見なされる）が Web サイトに初めてリクエストした場合、 [!DNL Sensor] は Web サーバーと連携して永続的な Cookie を設定します ( デフォルトでは [!DNL cs(cookie)(v1st)]) で、システム内の内部的には [!DNL x-trackingid]. この cookie は、その訪問者が Web サイトに対して最初におこなったリクエストで 1 回だけ設定されます。 その後、ブラウザーが将来 Web サイトでリクエスト（ページまたは埋め込みオブジェクトのリクエスト）をおこなうたびに、その訪問者から収集されます。

永続的な cookie を受け入れるかどうかは、ブラウザーの判断に従います。 永続的な cookie のブロックを選択した場合でも、ページビュー要求はログに記録されますが、IP フィールドや UserAgent フィールドで Hash 変換を使用するなど、訪問者を識別する代替の方法を実装しない限り、Web サイト上の特定の訪問者やセッションには関連付けられません。

>[!NOTE]
>
>サイト実験は、使用される訪問者識別の唯一の方法が [!DNL Sensor] 永続的な cookie メソッドを設定します。 J2EE サーバー (JBoss、Tomcat、WebLogic、WebSphere) 上で動作するセンサーは、対照実験をサポートしていません。

対照実験の間、cookie を受け入れないユーザーは、1 回のクリックから次のクリックまで、異なる実験グループに配置できます。 これは、で Broken Session Filter をオフにしてテスト分析を実行した場合にのみ問題になります。 [!DNL Insight]：このAdobeは推奨されません。

Broken Session Filter の詳細については、* [!DNL Insight] ユーザーガイド*。

実験中に訪問者が cookie をクリアした場合、訪問者には新しい cookie が割り当てられ、別のグループに割り当てられている可能性があります。 Adobeは訪問者を新規と識別するので、実験は無効にはなりません。
