---
description: InsightサーバーFSUのインストールおよび管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。
solution: Insight
title: InsightサーバーFSUのインストール手順
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# InsightサーバーFSUのインストール手順{#installation-procedures-for-an-insight-server-fsu}

InsightサーバーFSUのインストールおよび管理用の設定の手順は、InsightサーバーDPUのインストールおよび設定の手順と非常に似ています。

Windows 2012 Serverで *MS System Center Endpoint Protectionを使用する場合* 、次の実行可能ファイルを除外プロセスに追加する必要 **があります。**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

FSUをインストールおよび設定する [!DNL Insight Server] には、次のタスクを実行する必要があります。

1. プログラムファイル [!DNL Insight Server] をインストールします。
1. デジタル証明書をイ [!DNL Insight Server] ンストールします。
1. ファイル内のポート設定を確認 [!DNL Communications.cfg] します。
1. ファイルを変 [!DNL Access Control.cfg] 更して、からの管理アクセスを許可 [!DNL the Server] しま [!DNL the Client]す。
1. ファイルを変 [!DNL server.address] 更して、サーバーのネットワークの場所を定義します。
1. 説明に従って、Windowsのメモリ使用率パラメータを設定します。
1. 説明に従 [!DNL Insight Server] って、Windowsサービスとして登録します。

   FSU用のデータソース、権限および通信を設定する手順については、『データセッ [!DNL Insight Server] ト設定ガイド』を *参照してください*。

