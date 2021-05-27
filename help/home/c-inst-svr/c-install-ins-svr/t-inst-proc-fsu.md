---
description: InsightサーバーFSUをインストールし、管理用に設定する手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。
title: Insight サーバー FSU のインストール手順
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight サーバー FSU のインストール手順{#installation-procedures-for-an-insight-server-fsu}

InsightサーバーFSUをインストールし、管理用に設定する手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。

Windows 2012 Serverの&#x200B;*MS System Center Endpoint Protection*&#x200B;の場合、これらの実行ファイルを&#x200B;**除外プロセス**&#x200B;に追加する必要があります。

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

[!DNL Insight Server] FSUをインストールして設定するには、次のタスクを実行する必要があります。

1. [!DNL Insight Server]プログラムファイルをインストールします。
1. [!DNL Insight Server]電子証明書をインストールします。
1. [!DNL Communications.cfg]ファイルのポート設定を確認します。
1. [!DNL Access Control.cfg]ファイルを変更し、[!DNL the Client]から[!DNL the Server]への管理アクセスを許可します。
1. [!DNL server.address]ファイルを変更して、サーバーのネットワークの場所を定義します。
1. 説明に従って、Windowsのメモリ使用率のパラメータを設定します。
1. 説明に従って、Windowsサービスとして[!DNL Insight Server]を登録します。

   [!DNL Insight Server] FSUのデータソース、権限、通信を設定する手順については、『*データセット設定ガイド*』を参照してください。
