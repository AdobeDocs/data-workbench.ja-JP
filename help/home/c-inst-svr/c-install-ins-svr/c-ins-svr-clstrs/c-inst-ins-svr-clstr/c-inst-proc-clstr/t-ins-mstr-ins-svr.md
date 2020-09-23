---
description: クラスターを使用するには、クラスター内の1つのInsightサーバーを、マスターInsightサーバーとして機能するように指定する必要があります。
solution: Analytics
title: マスター Insight サーバーのインストール
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# マスター Insight サーバーのインストール{#installing-the-master-insight-server}

クラスターを使用するには、クラスター内の1つのInsightサーバーを、マスターInsightサーバーとして機能するように指定する必要があります。

セッションの開始時に、 [!DNL Insight] またはマスターに [!DNL Report] 接続するなどのクライアントコンポーネント [!DNL Insight Server] 。 セッション中の後続のポイントでは、クライアントは、クエリを実行するためにクラスター [!DNL Insight Servers] 内の他のクラスターと接続する場合があります。 クライアントとクラスター内の他方との間の以降の接続 [!DNL Insight Servers] は、マスターによってブロークされ、クライアント [!DNL Insight Server] に対して透過的に行われます。

クライアントとクラスター内の他のクラスター間のブローカリング接続 [!DNL Insight Servers] に加え、マスターは、クラスター全体の中央管理ポイント [!DNL Insight Server] として機能します。 クラスターを管理する場合は、マスターを更新し [!DNL Insight Server]ます。 マスターに対して行った管理上の変更は、クラスター内 [!DNL Insight Server] の他のユーザー [!DNL Insight Servers] によって取得されます。

**マスターをインストールするには[!DNL Insight Server]**

1. どのマシンがマスターとして機能するかを決定し [!DNL Insight Server]ます。
1. このマシンに(通常 [!DNL Insight Server] は [!DNL Insight Server] FSU)をインストールし、設定します( [Insightサーバーを参照](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md))。
1. 「 [!DNL Insight] ユーザガイド [!DNL Insight Server]*[!DNL Insight]*」の説明に従って、マスターへの接続をインストールし、設定します。
