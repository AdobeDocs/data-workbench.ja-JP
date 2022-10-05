---
description: Insight サーバー FSU をインストールし、管理用に設定する手順は、Insight サーバー DPU をインストールおよび設定する手順と非常に似ています。
title: Insight サーバー FSU のインストール手順
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight サーバー FSU のインストール手順{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

Insight サーバー FSU をインストールし、管理用に設定する手順は、Insight サーバー DPU をインストールおよび設定する手順と非常に似ています。

の場合 *MS System Center エンドポイント保護* Windows 2012 Server では、次の実行ファイルを **除外されたプロセス：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

をインストールして設定するには、以下を実行します。 [!DNL Insight Server] FSU では、次のタスクを実行する必要があります。

1. のインストール [!DNL Insight Server] プログラムファイル。
1. のインストール [!DNL Insight Server] 電子証明書。
1. でポート設定を確認します。 [!DNL Communications.cfg] ファイル。
1. を変更します。 [!DNL Access Control.cfg] ～への管理アクセスを許可するファイル [!DNL the Server] から [!DNL the Client].
1. を変更します。 [!DNL server.address] ファイルを使用して、サーバーのネットワークの場所を定義します。
1. 説明に従って、Windows のメモリ使用率のパラメータを設定します。
1. 登録 [!DNL Insight Server] を Windows サービスとして使用する場合は、を参照してください。

   のデータソース、権限、通信を設定する手順については、 [!DNL Insight Server] FSU( *データセット設定ガイド*.
