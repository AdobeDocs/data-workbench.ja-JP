---
description: Insight ServerReplication Serviceを使用すると、収集され、保存されたイベントデータをInsight Serverの1台のマシンから別のInsight Serverのマシンに送信できます。
solution: Insight
title: レプリケーションサービスのインストール
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# レプリケーションサービスのインストール{#installing-the-replication-service}

Insight ServerReplication Serviceを使用すると、収集され、保存されたイベントデータをInsight Serverの1台のマシンから別のInsight Serverのマシンに送信できます。

通常、データが収集され、格納されるマシンは、マシンとして実行するように設定され [!DNL Repeater] ます。 リピータ機 [能を参照してくださ](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)い。 ファイ [!DNL Replication Service]ルによって設定さ [!DNL Replicate.cfg] れるを使用すると、マシ [!DNL Insight Server] ンはマシンからデータを取得し、ローカル [!DNL Repeater] に保存できます。 このマ [!DNL Insight Server] シンはターゲットマシンと呼ばれます。 複数のDPU [!DNL Insight Server] を1つのDPUに接続して、複数のデ [!DNL Repeater] ータセットに含めるイベントデータのコピーをリクエストできます。

複数の層のファイアウォー [!DNL Replication Service] ルを持つネットワークインフラストラクチャでを使用すると、ファイアウォールで分離されたコンポーネント間で、単一ポートから単一ポートへの通信を実現できます。

**をインストールするには[!DNL Replication Service]**

このファ [!DNL Replicate.cfg] イルは、インストールの一部としてインストールされ [!DNL Insight Server] ます。 このファイルは、インストールディレクトリ [!DNL Components] のフォルダ内にあ [!DNL Insight Server] ります。 このファイルをお持ちでない場合は、アドビにお問い合わせください。
