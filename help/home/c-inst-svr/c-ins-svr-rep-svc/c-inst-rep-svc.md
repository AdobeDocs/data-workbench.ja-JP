---
description: Insight Serverレプリケーションサービスを使用すると、1台のInsightサーバーマシンで収集および保存されたイベントデータを別のInsightサーバーマシンに送信できます。
title: レプリケーションサービスのインストール
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# レプリケーションサービスのインストール{#installing-the-replication-service}

Insight Serverレプリケーションサービスを使用すると、1台のInsightサーバーマシンで収集および保存されたイベントデータを別のInsightサーバーマシンに送信できます。

通常、データが収集され、格納されるマシンは[!DNL Repeater]マシンとして実行するように設定されます。 [リピータ機能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)を参照してください。 [!DNL Replication Service]（[!DNL Replicate.cfg]ファイルで設定）を使用すると、[!DNL Insight Server]マシンで[!DNL Repeater]マシンからデータを取得し、ローカルに保存できます。 [!DNL Insight Server]マシンはターゲットマシンと呼ばれます。 複数の[!DNL Insight Server] DPUを1つの[!DNL Repeater]に接続して、複数のデータセットに含めるイベントデータのコピーをリクエストできます。

複数のレイヤーのファイアウォールを持つネットワークインフラストラクチャで[!DNL Replication Service]を使用すると、ファイアウォールで分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

**をインストールするには、以下を実行します。[!DNL Replication Service]**

[!DNL Replicate.cfg]ファイルは、[!DNL Insight Server]インストールの一部としてインストールする必要があります。 このファイルは、[!DNL Insight Server]インストールディレクトリの[!DNL Components]フォルダー内にあります。 このファイルがない場合は、Adobeにお問い合わせください。
