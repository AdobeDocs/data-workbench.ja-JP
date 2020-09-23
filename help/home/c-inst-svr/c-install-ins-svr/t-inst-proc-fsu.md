---
description: InsightサーバーFSUのインストールと管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。
solution: Analytics
title: Insight サーバー FSU のインストール手順
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---


# Insight サーバー FSU のインストール手順{#installation-procedures-for-an-insight-server-fsu}

InsightサーバーFSUのインストールと管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。

Windows 2012 Serverの *MS System Center Endpoint Protection* の場合、次の実行可能ファイルを **除外されたプロセスに追加する必要があります。**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

FSUをインストールして設定するには、次のタスクを実行する必要があり [!DNL Insight Server] ます。

1. プログラムファイルをインストールし [!DNL Insight Server] ます。
1. デジタル証明書をインスト [!DNL Insight Server] ールします。
1. ファイル内のポート設定を確認し [!DNL Communications.cfg] ます。
1. からの管理アクセスを許可する [!DNL Access Control.cfg] ファイルを変更 [!DNL the Server] し [!DNL the Client]ます。
1. サーバーのネットワークの場所を定義する [!DNL server.address] ファイルを変更します。
1. 説明に従って、Windowsのメモリ使用率のパラメータを設定します。
1. 説明 [!DNL Insight Server] に従って、Windowsサービスとして登録します。

   FSU用のデータソース、権限および通信を設定する手順については、『デー [!DNL Insight Server] タセット設定ガイド **』を参照してください。

