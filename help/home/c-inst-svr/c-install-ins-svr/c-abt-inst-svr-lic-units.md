---
description: Insight Serverは、2種類のライセンスで使用できます。
solution: Insight
title: Insight Serverライセンスユニットについて
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Serverライセンスユニットについて{#about-insight-server-license-units}

Insight Serverは、2種類のライセンスで使用できます。

次に、2つのライセンスの種類を示します。

* [データ処理ユニット(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [ファイルサーバーユニット（FSU）](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## データ処理ユニット(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

このタイプのデータ [!DNL Insight Server] は、アドビのデータセットのデータを処理、保存および提供できます。 It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). DPUとは、クライアントとの間で直接 [!DNL Insight Server] やり取りを行う [!DNL Insight] タイ [!DNL Report] プのことです。

DPUをインストールする場合は、 [!DNL Insight Server] 『InsightサーバーDPU [のインストール手順』を参照してください](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)。

## ファイルサーバーユニット（FSU）{#section-8f3a5c8521a34913bbed10f5794b1a0a}

このタイプのサーバーは、1つ以上のイベントデータ複製インスタンス（特別な使用ライセンスで提供される機能）からイベントデータを受け取って保存し、アドビのデータセットを構築するために1つ以上の [!DNL Sensor][!DNL Repeater][!DNL Insight Server] Data Processing Unit(DPU)にデータをストリーミングするように設定されます。 DPUは、イベントデータのDPUへの転送を最適化するプロトコルを使用してFSUと通信し、通常のファイルサーバー上のログファイルを維持するよりも大幅に高速です。 The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

FSUをインストールする場合は、 [!DNL Insight Server] 『InsightサーバーFSUの [インストール手順』を参照してください](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。
