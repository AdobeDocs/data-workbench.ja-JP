---
description: Insightサーバーのクライアント(Report and Insight)は、Insightサーバーを指すのに共通の名前を使用します。
title: サーバーのネットワーク位置の定義
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# サーバーのネットワーク位置の定義{#defining-the-server-s-network-location}

Insightサーバーのクライアント(Report and Insight)は、Insightサーバーを指すのに共通の名前を使用します。

例えば、[!DNL Insight]または[!DNL Report]を[!DNL Insight Server]に接続する場合、サーバーは共通名（例えば[!DNL Server.MyCompany.com]）で識別します。 内部的に、クライアントは、要求をサーバーに送信する前に、共通名を数値のIPアドレスに解決します。

共通名をIPアドレスに解決するために、[!DNL Insight Server’s]クライアントはアドレスファイルと呼ばれるローカルルックアップファイルを使用します。 アドレスファイルは、組織にインストールされている[!DNL Insight Servers]の共通名をリストし、その数値のIPアドレスを識別します。 クライアントは、[!DNL Insight Server]上のプロファイルを開くと、自動的にアドレスファイルのコピーを受け取ります。

クライアントが[!DNL Insight Server]に対して要求を発行すると、アドレスファイルを通じてサーバーの共通名の解決を試みます。 アドレスファイルが要求されたサーバーのIPアドレスを識別する場合、クライアントは要求を指定されたアドレスにルーティングします。 アドレスが定義されていない場合（例えば、アドレスファイルでサーバーの共通名が定義されていない場合）、要求は失敗します。 必要に応じて、クライアントのアドレスファイルに名前が定義されていない場合は、オペレーティング環境の通常のDomain Naming Service(DNS)メカニズムを使用してアドレスを解決するようにクライアントを設定できます。 手順については、次の節の[NetworkLocationパラメーターテーブル](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05)のParentパラメーターを参照してください。
