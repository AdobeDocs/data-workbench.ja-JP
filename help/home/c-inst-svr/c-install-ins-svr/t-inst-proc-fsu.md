---
description: InsightサーバーFSUのインストールと管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。
title: Insight サーバー FSU のインストール手順
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight サーバー FSU のインストール手順{#installation-procedures-for-an-insight-server-fsu}

InsightサーバーFSUのインストールと管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。

Windows 2012 Serverの&#x200B;*MS System Center Endpoint Protection*&#x200B;の場合、これらの実行可能ファイルを&#x200B;**除外されたプロセスに追加する必要があります：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

[!DNL Insight Server] FSUをインストールして構成するには、次のタスクを実行する必要があります。

1. [!DNL Insight Server]プログラムファイルをインストールします。
1. [!DNL Insight Server]デジタル証明書をインストールします。
1. [!DNL Communications.cfg]ファイルのポート設定を確認します。
1. [!DNL Access Control.cfg]ファイルを変更して、[!DNL the Client]から[!DNL the Server]への管理アクセスを許可します。
1. [!DNL server.address]ファイルを変更して、サーバーのネットワークの場所を定義します。
1. 説明に従って、Windowsのメモリ使用率のパラメータを設定します。
1. [!DNL Insight Server]をWindowsサービスとして登録します。

   [!DNL Insight Server] FSU用のデータソース、権限および通信を設定する手順については、『*データセット設定ガイド*』を参照してください。
