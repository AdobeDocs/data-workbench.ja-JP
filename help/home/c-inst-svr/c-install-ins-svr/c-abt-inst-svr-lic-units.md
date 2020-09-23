---
description: Insight Serverは、2種類のライセンスで使用できます。
solution: Analytics
title: Insight サーバーのライセンスユニットについて
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# Insight サーバーのライセンスユニットについて{#about-insight-server-license-units}

Insight Serverは、2種類のライセンスで使用できます。

次に、2つのライセンスの種類を示します。

* [データ処理ユニット(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [ファイルサーバーユニット（FSU）](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## データ処理ユニット(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

この種のデータは、Adobeデータセットのデータを処理、保存および提供するこ [!DNL Insight Server] とができます。 It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). DPUとは、クライアントとクライアントが直接やり取り [!DNL Insight Server] を行うDPUの種類 [!DNL Insight] で [!DNL Report] す。

DPUをインストールする場合は、『Insight [!DNL Insight Server] サーバーDPUの [インストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)』を参照してください。

## ファイルサーバーユニット（FSU）{#section-8f3a5c8521a34913bbed10f5794b1a0a}

このタイプのサーバは、1つ以上のイベントデータ複製インスタンス(特別な使用ライセンスで提供される [!DNL Sensor] 機能)からイベントデータを受け取って保存し、Adobeデータセットを構築するために1つ以上の [!DNL Repeater][!DNL Insight Server] データ処理ユニット(DPU)にストリーミングするように構成されます。 DPUは、イベントデータのDPUへの転送を最適化するプロトコルを使用してFSUと通信し、通常のファイルサーバーでのログファイルの保守よりも大幅に高速です。 The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

FSUをインストールする場合は、『Insight [!DNL Insight Server] サーバーFSUの [インストール手順](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)』を参照してください。
