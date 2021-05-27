---
description: Insightサーバーのクライアント(Report and Insight)は、共通名を使用してInsightサーバーを参照します。
title: サーバーのネットワーク位置の定義
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# サーバーのネットワーク位置の定義{#defining-the-server-s-network-location}

Insightサーバーのクライアント(Report and Insight)は、共通名を使用してInsightサーバーを参照します。

例えば、[!DNL Insight]または[!DNL Report]を[!DNL Insight Server]に接続する場合、サーバーは共通名（例：[!DNL Server.MyCompany.com]）で識別されます。 クライアントは、サーバーに要求を送信する前に、共通名を数値IPアドレスに解決します。

共通名をIPアドレスに解決するには、[!DNL Insight Server’s]クライアントは、アドレスファイルと呼ばれるローカルルックアップファイルを使用します。 アドレスファイルには、組織にインストールされている[!DNL Insight Servers]の共通名と、その数値IPアドレスが記述されています。 クライアントは、[!DNL Insight Server]上のプロファイルを開くと、アドレスファイルのコピーを自動的に受け取ります。

クライアントが[!DNL Insight Server]に対して要求を発行すると、アドレスファイルを通じてサーバの共通名の解決を試みます。 アドレスファイルが要求されたサーバのIPアドレスを識別する場合、クライアントは要求を指定されたアドレスにルーティングする。 アドレスが定義されていない場合（例えば、アドレスファイルでサーバーの共通名が定義されていない場合）、リクエストは失敗します。 必要に応じて、クライアントのアドレスファイルに名前が定義されていない場合は、オペレーティング環境の通常のDNS(Domain Naming Service)メカニズムを使用してアドレスを解決するようにクライアントを設定できます。 手順については、次の節の[NetworkLocation Parametersテーブル](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05)のParentパラメーターを参照してください。
