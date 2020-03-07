---
description: Insightサーバークラスターは、Insightおよびレポートのユーザーに対して処理およびアクセス可能にするデータの量が、単一のInsightサーバーの容量を超える場合に必要です。
solution: Insight
title: Insightサーバークラスターについて
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insightサーバークラスターについて{#about-insight-server-clusters}

Insightサーバークラスターは、Insightおよびレポートのユーザーに対して処理およびアクセス可能にするデータの量が、単一のInsightサーバーの容量を超える場合に必要です。

クラスターを設定す [!DNL Insight Server] ることで、1つの分析データセットをクラスター内の複数のマシンに配布し、複数のマシンの処理能力を活用できま [!DNL Insight Servers]す。

クラスターの実装の最初の手順は、ク [!DNL Insight Server] ラスター内のマシンを [!DNL Insight Server] 割り当てることです。 最初に設 [!DNL Insight Server] 定したマシンは、マスター [!DNL Insight Server] (プライマリとも呼ばれ [!DNL Insight Server]ます)です。

>[!NOTE]
>
>ファイルサーバーユニット(FSU) [!DNL Insight Server] を使用している場合は、FSUをマスターとして設定することをお勧めしま [!DNL Insight Server]す。 FSUの設定について詳しくは、『データセット設定ガイド』を *参照してください*。

マスターは、 [!DNL Insight Server] クラスター内の他の(処理サ [!DNL Insight Servers] ーバーと呼ばれる、または場合によってはクエリーサーバーと呼ばれる)とおよびのインスタンスとの間の通信を管 [!DNL Insight] 理しま [!DNL Report]す。 特定のデータセットの場合、ログファイルの処理は、設定ファイルで指定された（1つ以上の） [!DNL Insight Servers] マスターまたは処理に対して行 [!DNL Insight Server] われます。 クラスター環境で作業する場合、イ [!DNL Insight] ンストールはマスターにアクセスするように設定さ [!DNL Insight Server]れますが、クエリーはクラスター内の任意のユーザーが [!DNL Insight Servers] 処理できます。

>[!NOTE]
>
>**PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site. >
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>この章の説明は、5を超えるクラスターを作成す [!DNL Insight Server] る場合には適用されません(5) [!DNL Insight Servers]。 システム要件と、5を超えるクラスターのプロファイル設定の推奨事項を入手するには、アドビにお問い合わせくださ [!DNL Insight Servers]い。

