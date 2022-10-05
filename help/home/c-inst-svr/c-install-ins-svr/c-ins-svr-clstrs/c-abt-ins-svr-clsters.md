---
description: Insight サーバークラスターは、Insight とレポートのユーザーが処理してアクセスできるデータの量が、1 台の Insight サーバーの容量を超える場合に必要です。
title: Insight サーバークラスターについて
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---

# Insight サーバークラスターについて{#about-insight-server-clusters}

{{eol}}

Insight サーバークラスターは、Insight とレポートのユーザーが処理してアクセスできるデータの量が、1 台の Insight サーバーの容量を超える場合に必要です。

次の項目を設定して、 [!DNL Insight Server] クラスターを使用すると、1 つのクラスター内の複数のマシンに 1 つの分析データセットを配布して、複数のマシンの処理能力を活用できます [!DNL Insight Servers].

の実装の最初の手順 [!DNL Insight Server] クラスターは、 [!DNL Insight Server] クラスター内のマシン。 最初の [!DNL Insight Server] 設定したマシンがマスターです [!DNL Insight Server] （プライマリと呼ばれる場合もあります） [!DNL Insight Server]) をクリックします。

>[!NOTE]
>
>を使用している場合、 [!DNL Insight Server] FSU(File Server Unit) を使用する場合、Adobeでは FSU をマスターとして設定することをお勧めします [!DNL Insight Server]. FSU の設定について詳しくは、 *データセット設定ガイド*.

マスター [!DNL Insight Server] 相互の通信を管理する [!DNL Insight Servers] （処理サーバーと呼ばれる場合もあれば、クエリサーバーと呼ばれる場合もあります）と [!DNL Insight] および [!DNL Report]. 特定のデータセットに対して、ログファイルの処理は、指定された（1 つ以上の） [!DNL Insight Servers] （マスターまたは処理） [!DNL Insight Server] 設定ファイル。 クラスター環境で作業する場合、 [!DNL Insight] インストールは、マスターにアクセスするように設定されています [!DNL Insight Server]を使用できますが、クエリは任意の [!DNL Insight Servers] クラスター内で使用できます。

>[!NOTE]
>
>**PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。カスタムプロファイルは [!DNL PAServer.cfg] 予測分析プロファイル ([!DNL Server\Profiles\Predictive Analytics\Dataset]) をクリックします。 を設定します。 *マスターサーバ* このファイルで、 [!DNL PAServer.cfg] を実装サイトに追加します。
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>この章の手順は、 [!DNL Insight Server] 5 個を超える群れ [!DNL Insight Servers]. Adobeに連絡して、5 つ以上のクラスターの必要システム構成とプロファイル構成の推奨事項を取得してください [!DNL Insight Servers].
