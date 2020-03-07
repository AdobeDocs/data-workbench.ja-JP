---
description: クラスターを使用するには、クラスター内の1つのInsightサーバーをマスターInsightサーバーとして指定する必要があります。
solution: Insight
title: Master Insightサーバーのインストール
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Master Insightサーバーのインストール{#installing-the-master-insight-server}

クラスターを使用するには、クラスター内の1つのInsightサーバーをマスターInsightサーバーとして指定する必要があります。

セッションの開始時に、 [!DNL Insight] または [!DNL Report] マスターに接続するな [!DNL Insight Server] どのクライアントコンポーネント。 セッション中の後続のポイントで、クライアントはクラスター内の他のク [!DNL Insight Servers] ラスターと接続してクエリを実行できます。 クライアントとクラスター内の他のクライアント間のこれ [!DNL Insight Servers] らの後続の接続は、マスターによってブ [!DNL Insight Server] ロークされ、クライアントに対して透過的になります。

クライアントとクラスター内の他のクラスター間のブ [!DNL Insight Servers] ローカリング接続に加え、マスターはク [!DNL Insight Server] ラスター全体の中央管理ポイントとして機能します。 クラスターを管理する場合は、マスターを更新しま [!DNL Insight Server]す。 マスターに対して行った管理上の変更は、ク [!DNL Insight Server] ラスター内の別のユーザーによ [!DNL Insight Servers] って取得されます。

**マスターをインストールするには[!DNL Insight Server]**

1. どのマシンがマスターとして機能するかを決定しま [!DNL Insight Server]す。
1. このマシンに(通常 [!DNL Insight Server] はFSU)をインスト [!DNL Insight Server] ールし、設定します( [Insightサーバーを参照)](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)。
1. 『ユー [!DNL Insight] ザガイド』の説明に従って、マスタ [!DNL Insight Server] ーへの接続をインストー *[!DNL Insight]ルし設定します&#x200B;*。
