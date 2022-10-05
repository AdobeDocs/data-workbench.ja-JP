---
description: Insight サーバーは、2 つのライセンスタイプで使用できます。
title: Insight サーバーのライセンスユニットについて
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# Insight サーバーのライセンスユニットについて{#about-insight-server-license-units}

{{eol}}

Insight サーバーは、2 つのライセンスタイプで使用できます。

次の 2 種類のライセンスを示します。

* [データ処理ユニット (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [ファイルサーバーユニット（FSU）](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## データ処理ユニット (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

このタイプの [!DNL Insight Server] は、データセットのデータを処理、保存および提供できます。Adobeは、 必要に応じて、データセットの構築元となるソースデータを含むログファイルを保存したり、 [!DNL Insight Server] ファイルサーバーユニット (FSU)。 DPU は、 [!DNL Insight Server] そして [!DNL Insight] および [!DNL Report] クライアントは直接やり取りします。

をインストールする場合、 [!DNL Insight Server] DPU( [Insight サーバー DPU のインストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## ファイルサーバーユニット（FSU） {#section-8f3a5c8521a34913bbed10f5794b1a0a}

このタイプのサーバーは、1 つ以上のイベントデータを受信して保存するように設定されます [!DNL Sensor] またはイベントデータレプリケーションインスタンス [!DNL Repeater] （特別使用ライセンスで提供される機能）と、データを 1 つ以上の [!DNL Insight Server] データデータセットを構築するためのAdobe処理単位 (DPU)。 DPU は、イベントデータを DPU に転送する際に最適化するプロトコルを使用して FSU と通信し、通常のファイルサーバー上でログファイルを保持するよりも大幅に高速です。 FSU を使用すると、ログデータを低コストのストレージハードウェアに格納できるので、ハードウェアコストも削減され、複数の [!DNL Sensors] 一つを指す [!DNL Insight Server].

をインストールする場合、 [!DNL Insight Server] FSU( [Insight サーバー FSU のインストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
