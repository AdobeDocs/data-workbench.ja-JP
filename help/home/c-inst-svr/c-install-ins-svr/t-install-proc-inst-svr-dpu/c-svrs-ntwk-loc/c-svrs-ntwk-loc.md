---
description: Insightサーバーのクライアント(Report and Insight)は、Insightサーバーを指すのに共通の名前を使用します。
solution: Analytics
title: サーバーのネットワーク位置の定義
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---


# サーバーのネットワーク位置の定義{#defining-the-server-s-network-location}

Insightサーバーのクライアント(Report and Insight)は、Insightサーバーを指すのに共通の名前を使用します。

例えば、接続 [!DNL Insight] やサーバー [!DNL Report] への接続時に、サーバーを共通名( [!DNL Insight Server][!DNL Server.MyCompany.com]など)で識別します。 内部的に、クライアントは、要求をサーバーに送信する前に、共通名を数値のIPアドレスに解決します。

共通名をIPアドレスに解決するには、 [!DNL Insight Server’s] クライアントはアドレスファイルと呼ばれるローカルルックアップファイルを使用します。 アドレスファイルリストは、組織に [!DNL Insight Servers] インストールされている共通名を識別し、数値のIPアドレスを識別します。 クライアントは、アドレスファイル上のプロファイルを開くと、自動的にアドレスファイルのコピーを受け取り [!DNL Insight Server]ます。

クライアントがサーバーに対する要求を発行すると [!DNL Insight Server]、アドレスファイルを通じてサーバーの共通名の解決が試行されます。 アドレスファイルが要求されたサーバーのIPアドレスを識別する場合、クライアントは要求を指定されたアドレスにルーティングします。 アドレスが定義されていない場合（例えば、アドレスファイルでサーバーの共通名が定義されていない場合）、要求は失敗します。 必要に応じて、クライアントのアドレスファイルに名前が定義されていない場合は、オペレーティング環境の通常のDomain Naming Service(DNS)メカニズムを使用してアドレスを解決するようにクライアントを設定できます。 手順については、次の節のNetworkLocationパラメーターの表 [](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) 「Parent」パラメーターを参照してください。
