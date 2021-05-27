---
description: クラスターを使用するには、マスターInsightサーバーとして機能するクラスター内のInsightサーバーを1つ指定する必要があります。
title: マスター Insight サーバーのインストール
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# マスター Insight サーバーのインストール{#installing-the-master-insight-server}

クラスターを使用するには、マスターInsightサーバーとして機能するクラスター内のInsightサーバーを1つ指定する必要があります。

[!DNL Insight]や[!DNL Report]などのクライアントコンポーネントは、セッションの開始時にマスター[!DNL Insight Server]に接続します。 セッション中の後続のポイントで、クライアントはクラスター内の他の[!DNL Insight Servers]に接続してクエリを実行できます。 クライアントとクラスタ内の他の[!DNL Insight Servers]との後続の接続は、マスター[!DNL Insight Server]によってブロークされ、クライアントに対して透過的です。

クライアントとクラスタ内の他の[!DNL Insight Servers]との間のブローカ接続に加えて、マスター[!DNL Insight Server]がクラスタ全体の中央管理ポイントとして機能します。 クラスターを管理する場合は、マスター[!DNL Insight Server]を更新します。 マスター[!DNL Insight Server]に加えた管理上の変更は、クラスター内の他の[!DNL Insight Servers]によって取得されます。

**マスターをインストールするには[!DNL Insight Server]**

1. マスター[!DNL Insight Server]として機能するマシンを決定します。
1. [Insightサーバー](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)の説明に従って、このマシンに[!DNL Insight Server]（通常は[!DNL Insight Server] FSU）をインストールし、設定します。
1. [!DNL Insight]をインストールし、*[!DNL Insight]ユーザーガイド*&#x200B;の説明に従って、マスター[!DNL Insight Server]への接続を設定します。
