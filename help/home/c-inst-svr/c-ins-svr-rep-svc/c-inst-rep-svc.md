---
description: Insight ServerReplication Serviceを使用すると、1台のInsight Serverマシンで収集および保存されたイベントデータを別のInsight Serverマシンに送信できます。
solution: Analytics
title: レプリケーションサービスのインストール
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---


# レプリケーションサービスのインストール{#installing-the-replication-service}

Insight ServerReplication Serviceを使用すると、1台のInsight Serverマシンで収集および保存されたイベントデータを別のInsight Serverマシンに送信できます。

通常、データが収集され、保存されるマシンは、 [!DNL Repeater] マシンとして実行するように設定されます。 「 [リピータ機能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)」を参照してください。 は、 [!DNL Replication Service]ファイルによって設定され [!DNL Replicate.cfg] るもので、マシンが [!DNL Insight Server] マシンからデータを取得し、ローカルに格納できるようにし [!DNL Repeater] ます。 この [!DNL Insight Server] マシンは、ターゲットマシンと呼ばれます。 複数の [!DNL Insight Server] DPUを1つのDPUに接続して、イベントデータのコピー [!DNL Repeater] をリクエストし、複数のデータセットに組み込むことができます。

複数のレイヤーのファイアウォールを持つネットワークインフラストラクチャ [!DNL Replication Service] でを使用すると、ファイアウォールによって分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

**をインストールするには[!DNL Replication Service]**

この [!DNL Replicate.cfg] ファイルは、インストールの一部としてインストールする必要があり [!DNL Insight Server] ます。 このファイルは、インストールディレクトリの [!DNL Components] フォルダ内にあり [!DNL Insight Server] ます。 このファイルがない場合は、Adobeにお問い合わせください。
