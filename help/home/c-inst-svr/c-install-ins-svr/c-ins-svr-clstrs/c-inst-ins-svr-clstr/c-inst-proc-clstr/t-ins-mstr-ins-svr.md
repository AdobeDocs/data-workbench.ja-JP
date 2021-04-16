---
description: クラスターを使用するには、クラスター内の1つのInsightサーバーを、マスターInsightサーバーとして機能するように指定する必要があります。
title: マスター Insight サーバーのインストール
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# マスター Insight サーバーのインストール{#installing-the-master-insight-server}

クラスターを使用するには、クラスター内の1つのInsightサーバーを、マスターInsightサーバーとして機能するように指定する必要があります。

[!DNL Insight]や[!DNL Report]などのクライアントコンポーネントは、セッションの開始時にマスター[!DNL Insight Server]に接続します。 セッション中の後続のポイントでは、クライアントはクラスター内の他の[!DNL Insight Servers]に接続してクエリを実行する場合があります。 クライアントとクラスター内の他の[!DNL Insight Servers]との接続は、マスター[!DNL Insight Server]によってブロークされ、クライアントに対して透過的になります。

クライアントとクラスター内の他の[!DNL Insight Servers]間の接続の分離に加え、マスター[!DNL Insight Server]は、クラスター全体の中央管理ポイントとして機能します。 クラスターを管理する場合は、マスター[!DNL Insight Server]を更新します。 マスター[!DNL Insight Server]に対して行った管理上の変更は、クラスター内の他の[!DNL Insight Servers]によって取得されます。

**マスターをインストールするには[!DNL Insight Server]**

1. どのマシンがマスター[!DNL Insight Server]として機能するかを決定します。
1. [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)の説明に従って、このマシンに[!DNL Insight Server]（通常は[!DNL Insight Server] FSU）をインストールし、設定します。
1. [!DNL Insight]をインストールし、*[!DNL Insight]ユーザーガイド*&#x200B;の説明に従って、マスター[!DNL Insight Server]への接続を設定します。
