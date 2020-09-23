---
description: リピーター機能を使用すると、Insight Server FSUは、1つ以上のソースからSensorで取得したイベントデータを受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsight Server FSUにデータを複製できます。
solution: Analytics
title: リピーター機能の設定
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 17%

---


# リピーター機能の設定{#configuring-repeater-functionality}

リピーター機能を使用すると、Insight Server FSUは、1つ以上のソースからSensorで取得したイベントデータを受け取り、Insight ServerReplicationサービスを実行する1つ以上のInsight Server FSUにデータを複製できます。

See [Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). この機能により、災害復旧のために冗長な設備へのデータ・レプリケーションが可能になります。 ターゲットサーバはネットワーククライアントとして機能し、ソースFSUに接続して、複数のデータセットに含めるイベントデータのコピーをリクエストします。

複数のレイヤーのファイアウォールを持つネットワークインフラストラクチャでリピータ機能を使用すると、ファイアウォールによって分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

[!DNL Repeater] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

をインストールするに [!DNL Repeater]は、次の2つの手順に従う必要があります。

* [Insight サーバー FSU のリピーター用の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [ターゲットマシンのアクセス制御の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

ネットワークファイアウォールで [!DNL Repeater] からのアクセスが許可されている場合 [!DNL Insight]は、Insightとリピーター間の接続の [作成の説明に従って接続を作成できます](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)。
