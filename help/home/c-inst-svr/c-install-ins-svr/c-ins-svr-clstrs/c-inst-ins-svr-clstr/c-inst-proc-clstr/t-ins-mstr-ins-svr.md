---
description: クラスターを使用するには、クラスター内の 1 つの Insight サーバーを、マスター Insight サーバーとして機能するように指定する必要があります。
title: マスター Insight サーバーのインストール
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# マスター Insight サーバーのインストール{#installing-the-master-insight-server}

{{eol}}

クラスターを使用するには、クラスター内の 1 つの Insight サーバーを、マスター Insight サーバーとして機能するように指定する必要があります。

クライアントコンポーネント [!DNL Insight] または [!DNL Report] マスターに接続 [!DNL Insight Server] をクリックします。 セッション中の後続のポイントで、クライアントは他の [!DNL Insight Servers] クエリを実行するクラスター内。 これ以降のクライアントと他のクライアント間の接続 [!DNL Insight Servers] クラスター内のは、マスターによってブロックされます [!DNL Insight Server] また、クライアントに対して透過的です。

クライアントと他のクライアントとの間のブローカリング接続に加えて [!DNL Insight Servers] クラスターで、マスター [!DNL Insight Server] は、クラスタ全体の中央管理ポイントとして機能します。 クラスタを管理する場合は、マスターを更新します [!DNL Insight Server]. マスターに加えた管理上の変更 [!DNL Insight Server] 他の [!DNL Insight Servers] クラスター内で使用します。

**マスターをインストールするには[!DNL Insight Server]**

1. マスターとして機能するマシンを決定します [!DNL Insight Server].
1. インストールと設定 [!DNL Insight Server] ( 通常 [!DNL Insight Server] FSU) をこのマシン上に配置します ( [Insight サーバー](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. インストール [!DNL Insight] マスターへの接続を設定します。 [!DNL Insight Server] 例えば、 *[!DNL Insight]ユーザーガイド*.
