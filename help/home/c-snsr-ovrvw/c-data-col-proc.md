---
description: Sensorは、従来データ収集に関与してきた人手の大部分を排除することで、インターネットチャネルからのデータ取得を自動化します。
solution: Analytics
title: データ収集プロセスの仕組み
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# データ収集プロセスの仕組み{#how-does-the-data-collection-process-work}

Sensorは、従来データ収集に関与してきた人手の大部分を排除することで、インターネットチャネルからのデータ取得を自動化します。

多くの場合、を使用するとデータ管理プロセス [!DNL Sensor] を大幅に簡略化できます。

今日の大規模なインターネット、エクストラネット、イントラネットのサイトは、多くの場合、一連のWebサーバー上で動作します。 生成されるログとデータは、管理に非常に大きく、扱いにくい場合があります。 例えば、サイトで30台のWebサーバーを実行している場合、通常は従業員(またはアウトソーシングのサービスプロバイダーの従業員)が30台のサーバーそれぞれのログファイルを取り込んで統合し、レポートを実行します。 各Webサーバー [!DNL Sensor] にインストールすると、このプロセス全体が自動化され、コストが削減され、データをリアルタイムで利用できるようになります。

このプロセスを自動化するには、各WebサーバーからWebサイト上のトラフィックに関する生の情報を直接収集します。 [!DNL Sensor] 取り込まれる生データはイベントデータと呼ば [!DNL Sensor] れ、Webサーバーがログファイルに記録するデータの種類と似ています。

このデータを取り込むために、Webサーバーが処理する各HTTP要求に関する情報がinstrumentationに [!DNL Sensor] 記録されます。 [!DNL Sensor] 次に、ネットワーク障害から保護する情報をバッファリングし、HTTP/S経由で指定した場所に情報を安全に送信 [!DNL data workbench server] します。

がデータを [!DNL data workbench server][!DNL .vsl] 受け取ると、ログファイルを高圧縮形式のファイルで処理および保存するので、非常に大量のデータを安価なハードウェアで簡単に管理できます。

ファイルで収集されるイベントデータフィールドにつ [!DNL Sensor] いて詳しくは、「 [!DNL .vsl] イベントデータレコードフィールド [](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)」を参照してください。
