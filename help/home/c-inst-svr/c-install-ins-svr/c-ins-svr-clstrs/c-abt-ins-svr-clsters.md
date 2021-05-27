---
description: Insightサーバークラスターは、Insightとレポートのユーザーがアクセスできるように処理するデータの量が、1台のInsightサーバーの容量を超える場合に必要です。
title: Insight サーバークラスターについて
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 11%

---

# Insight サーバークラスターについて{#about-insight-server-clusters}

Insightサーバークラスターは、Insightとレポートのユーザーがアクセスできるように処理するデータの量が、1台のInsightサーバーの容量を超える場合に必要です。

[!DNL Insight Server]クラスターを設定すると、1つの分析データセットを1つのクラスター内の複数のマシンに分散させて、複数の[!DNL Insight Servers]の処理能力を活用できます。

[!DNL Insight Server]クラスターの実装の最初の手順は、クラスター内の[!DNL Insight Server]マシンを割り当てることです。 最初に設定した[!DNL Insight Server]マシンは、マスター[!DNL Insight Server]（プライマリ[!DNL Insight Server]と呼ばれる場合もあります）です。

>[!NOTE]
>
>[!DNL Insight Server]ファイルサーバーユニット(FSU)を使用している場合は、FSUをマスター[!DNL Insight Server]として設定することをAdobeにお勧めします。 FSUの設定について詳しくは、『*データセット設定ガイド*』を参照してください。

マスター[!DNL Insight Server]は、クラスター内の他の[!DNL Insight Servers]（処理サーバーと呼ばれる場合や、クエリサーバーと呼ばれる場合もあります）と[!DNL Insight]および[!DNL Report]のインスタンスとの間の通信を管理します。 特定のデータセットに対して、ログファイル処理は、[!DNL Insight Server]設定ファイルで指定された[!DNL Insight Servers]（マスターまたは処理）に対しておこなわれます。 クラスター環境で作業する場合、[!DNL Insight]インストールはマスター[!DNL Insight Server]にアクセスするように設定されますが、クエリはクラスター内の任意の[!DNL Insight Servers]で処理できます。

>[!NOTE]
>
>**PAServer.cfg** ファイル：Insight Server に予測分析クラスタリングジョブを送信する場合は、サーバー側でクラスタリング送信を処理するように [!DNL PAServer.cfg] ファイルを設定する必要があります。カスタムプロファイルは、予測分析プロファイル([!DNL Server\Profiles\Predictive Analytics\Dataset])から[!DNL PAServer.cfg]を継承する必要があります。 このファイルに&#x200B;*マスターサーバー*&#x200B;を設定し、[!DNL PAServer.cfg]を実装サイトに保存します。
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
>この章の手順は、5個(5)[!DNL Insight Servers]を超える[!DNL Insight Server]クラスターの作成には適用されません。 Adobeに連絡して、5個[!DNL Insight Servers]を超えるクラスターの必要システム構成とプロファイル構成の推奨事項を入手してください。
