---
description: Insight ServerReplication Service を使用すると、収集され、保存されたイベントデータを、ある Insight Server マシンから別の Insight Server マシンに送信できます。
title: レプリケーションサービスのインストール
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# レプリケーションサービスのインストール{#installing-the-replication-service}

{{eol}}

Insight ServerReplication Service を使用すると、収集され、保存されたイベントデータを、ある Insight Server マシンから別の Insight Server マシンに送信できます。

通常、データが収集され、格納されるマシンは、 [!DNL Repeater] マシン。 詳しくは、 [リピーター機能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). この [!DNL Replication Service]( [!DNL Replicate.cfg] ファイル、有効 [!DNL Insight Server] からデータを取得するマシン [!DNL Repeater] をローカルに保存する必要があります。 この [!DNL Insight Server] マシンはターゲットマシンと呼ばれます。 複数 [!DNL Insight Server] DPU は 1 つの [!DNL Repeater] を使用して、複数のデータセットに含めるイベントデータのコピーをリクエストします。

以下を使用して、 [!DNL Replication Service] ファイアウォールで分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現するために、複数層のファイアウォールを持つネットワークインフラストラクチャで使用します。

**をインストールするには、以下を実行します。[!DNL Replication Service]**

この [!DNL Replicate.cfg] ファイルは、 [!DNL Insight Server] インストール。 ファイルは、 [!DNL Components] のフォルダー [!DNL Insight Server] インストールディレクトリ。 このファイルがない場合は、Adobeにお問い合わせください。
