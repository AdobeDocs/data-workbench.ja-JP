---
description: リピーター機能を使用すると、Insight サーバー FSU は、センサーで取得したイベントデータを 1 つ以上のソースから受け取り、Insight ServerReplication サービスを実行する 1 つ以上の Insight サーバー FSU にデータをレプリケートできます。
title: リピーター機能の設定
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 17%

---

# リピーター機能の設定{#configuring-repeater-functionality}

{{eol}}

リピーター機能を使用すると、Insight サーバー FSU は、センサーで取得したイベントデータを 1 つ以上のソースから受け取り、Insight ServerReplication サービスを実行する 1 つ以上の Insight サーバー FSU にデータをレプリケートできます。

詳しくは、 [Insight サーバーレプリケーションサービス](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92). この機能により、災害復旧の目的で冗長化された設備に対するデータ・レプリケーションが可能になります。 ターゲットサーバーはネットワーククライアントとして機能し、ソース FSU に接続して、複数のデータセットに含めるイベントデータのコピーをリクエストします。

複数層のファイアウォールを持つネットワークインフラストラクチャでリピーター機能を使用すると、ファイアウォールで分離されたコンポーネント間で、シングルポートからシングルポートへの通信を実現できます。

[!DNL Repeater] をインストール、設定および操作するための必要システム構成について詳しくは、*必要システム構成*&#x200B;のドキュメントを参照してください。

をインストールするには [!DNL Repeater]次の 2 つの手順に従って、一覧に表示される手順を実行する必要があります。

* [Insight サーバー FSU のリピーター用の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [ターゲットマシンのアクセス制御の設定](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

ネットワークファイアウォールがユーザーの [!DNL Repeater] から [!DNL Insight]を使用すると、 [Insight とリピーターとの接続の作成](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118).
