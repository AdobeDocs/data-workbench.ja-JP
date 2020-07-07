---
description: Insightサーバークラスターは、Insightおよびレポートのユーザーが処理し、アクセスできるようにするデータの量が、単一のInsightサーバーの容量を超える場合に必要です。
solution: Insight
title: Insight Server Clustersについて
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: 2c1b2adfe8bf479c2a8cbd150ed006be2336022c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 8%

---


# Insight Server Clustersについて{#about-insight-server-clusters}

Insightサーバークラスターは、Insightおよびレポートのユーザーが処理し、アクセスできるようにするデータの量が、単一のInsightサーバーの容量を超える場合に必要です。

クラスターを設定することで、1つの分析データセットをクラスター内の複数のマシンに配布し、複数のマシンの処理能力を活用でき [!DNL Insight Server][!DNL Insight Servers]ます。

クラスターの実装の最初の手順は、クラスター内の [!DNL Insight Server] マシンを割り当てるこ [!DNL Insight Server] とです。 最初に設定した [!DNL Insight Server] マシンは、マスター [!DNL Insight Server] (「プライマリ」と呼ばれる場合もあり [!DNL Insight Server]ます)です。

>[!NOTE]
>
>FSU( [!DNL Insight Server] ファイルサーバーユニット)を使用する場合は、FSUをマスターとして設定することをお勧めし [!DNL Insight Server]ます。 FSUの設定について詳しくは、『 *データセット設定ガイド*』を参照してください。

マスターは、クラスター内の他のサーバー(処理サーバー、場合によってはクエリサーバー) [!DNL Insight Server] とおよびのインスタンス間の通信 [!DNL Insight Servers] を管理 [!DNL Insight][!DNL Report]します。 特定のデータセットに対して、ログファイルの処理は、設定ファイルに指定された（1つ以上の）指定 [!DNL Insight Servers] された（マスターまたは処理）データに対して行われ [!DNL Insight Server] ます。 クラスター環境で作業する場合、 [!DNL Insight] インストールはマスターにアクセスするように設定され [!DNL Insight Server]ますが、クエリはクラスター [!DNL Insight Servers] 内の任意のユーザーが処理できます。

>[!NOTE]
>
>**PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ([!DNL Server\Profiles\Predictive Analytics\Dataset]). Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
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
>この章の説明は、5を超えるクラスターを作成する場合には適用されません( [!DNL Insight Server] 5) [!DNL Insight Servers]。 必要システム構成と、5を超えるクラスターのプロファイル構成の推奨事項を入手するには、アドビにお問い合わせくだ [!DNL Insight Servers]さい。
