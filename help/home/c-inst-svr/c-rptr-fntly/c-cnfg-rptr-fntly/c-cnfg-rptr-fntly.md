---
description: リピータ機能を使用すると、Insight Server FSUは、1つ以上のソースからSensorが取得したイベントデータを受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsight Server FSUにデータを複製できます。
solution: Insight
title: リピータ機能の設定
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# リピータ機能の設定{#configuring-repeater-functionality}

リピータ機能を使用すると、Insight Server FSUは、1つ以上のソースからSensorが取得したイベントデータを受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsight Server FSUにデータを複製できます。

詳しくは、 [Insight Server Replication Serviceを参照してください](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)。 この機能により、災害復旧のために冗長な設備へのデータ・レプリケーションが可能になります。 ターゲット・サーバはネットワーク・クライアントとして機能し、ソースFSUに接続して、複数のデータセットに含めるイベント・データのコピーをリクエストします。

複数のファイアウォールを持つネットワークインフラストラクチャでリピータ機能を使用すると、ファイアウォールで分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

[!DNL Repeater] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

をインストール [!DNL Repeater]するには、次の2つの手順に従う必要があります。

* [Repeater用のInsightサーバーFSUの設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [ターゲットコンピューターのアクセス制御の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

ネットワークファイアウォールでからのアクセ [!DNL Repeater] スが許可さ [!DNL Insight]れている場合は、「Insightとリピーター間の接続の作成」の説 [明に従って接続を作成できます](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)。
