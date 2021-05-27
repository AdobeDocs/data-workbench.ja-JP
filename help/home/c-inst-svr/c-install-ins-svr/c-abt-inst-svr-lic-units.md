---
description: Insightサーバーは、2つのライセンスタイプで使用できます。
title: Insight サーバーのライセンスユニットについて
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# Insight サーバーのライセンスユニットについて{#about-insight-server-license-units}

Insightサーバーは、2つのライセンスタイプで使用できます。

次の2種類のライセンスを示します。

* [データ処理ユニット(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [ファイルサーバーユニット（FSU）](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## データ処理ユニット(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

このタイプの[!DNL Insight Server]は、Adobeデータセットのデータを処理、保存、提供できます。 必要に応じて、データセットの構築元となるソースデータを含むログファイルを保存することも、[!DNL Insight Server]ファイルサーバーユニット(FSU)からデータを受け取ることもできます。 DPUは、[!DNL Insight]クライアントと[!DNL Report]クライアントが直接やり取りする[!DNL Insight Server]のタイプです。

[!DNL Insight Server] DPUをインストールする場合は、 [InsightサーバーDPUのインストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)を参照してください。

## ファイルサーバーユニット（FSU）{#section-8f3a5c8521a34913bbed10f5794b1a0a}

このタイプのサーバは、1つ以上の[!DNL Sensor]またはイベントデータレプリケーションインスタンス（特別な使用ライセンスが付属する[!DNL Repeater]機能）からイベントデータを受け取って保存し、Adobeデータセットを作成する1つ以上の[!DNL Insight Server]データ処理ユニット(DPU)にデータを送信します。 DPUは、イベントデータをDPUに転送する際に最適化するプロトコルを使用してFSUと通信し、通常のファイルサーバーでログファイルを保守するよりも大幅に高速です。 FSUを使用することで、低コストのストレージハードウェアにログデータを格納でき、複数の[!DNL Sensors]が単一の[!DNL Insight Server]を指すことで、管理の複雑さも軽減されます。

[!DNL Insight Server] FSUをインストールする場合は、 [InsightサーバーFSUのインストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)を参照してください。
