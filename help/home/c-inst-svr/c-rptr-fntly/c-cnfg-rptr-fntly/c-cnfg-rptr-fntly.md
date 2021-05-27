---
description: リピーター機能を使用すると、InsightサーバーFSUは、センサーで取得したイベントデータを1つ以上のソースから受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsightサーバーFSUにデータをレプリケートできます。
title: リピーター機能の設定
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 17%

---

# リピーター機能の設定{#configuring-repeater-functionality}

リピーター機能を使用すると、InsightサーバーFSUは、センサーで取得したイベントデータを1つ以上のソースから受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsightサーバーFSUにデータをレプリケートできます。

[Insightサーバーレプリケーションサービス](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)を参照してください。 この機能により、災害復旧用に冗長な設備に対するデータ・レプリケーションが可能になります。 ターゲットサーバーはネットワーククライアントとして機能し、ソースFSUに接続して、複数のデータセットに含めるイベントデータのコピーをリクエストします。

複数のレイヤーのファイアウォールを持つネットワークインフラストラクチャでリピータ機能を使用すると、ファイアウォールで分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

[!DNL Repeater] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

[!DNL Repeater]をインストールするには、次の2つの手順に従う必要があります。

* [Insight サーバー FSU のリピーター用の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [ターゲットマシンのアクセス制御の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

[!DNL Insight]からの[!DNL Repeater]へのアクセスがネットワークファイアウォールによって許可されている場合は、 [Insightとリピーターの間の接続の作成](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)の説明に従って、接続を作成できます。
