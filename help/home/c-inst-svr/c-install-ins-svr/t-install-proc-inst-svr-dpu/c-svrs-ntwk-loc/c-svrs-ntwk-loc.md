---
description: Insight サーバーのクライアント (Report and Insight) は、Insight サーバーを指す共通名を使用します。
title: サーバーのネットワーク位置の定義
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# サーバーのネットワーク位置の定義{#defining-the-server-s-network-location}

{{eol}}

Insight サーバーのクライアント (Report and Insight) は、Insight サーバーを指す共通名を使用します。

例えば、 [!DNL Insight] または [!DNL Report] から [!DNL Insight Server]を使用する場合、サーバーは共通名 ( 例： [!DNL Server.MyCompany.com]) をクリックします。 内部的に、クライアントは、サーバーに要求を送信する前に、共通名を数値 IP アドレスに解決します。

共通名を IP アドレスに解決するには、以下を実行します。 [!DNL Insight Server’s] クライアントは、アドレスファイルと呼ばれるローカル参照ファイルを使用します。 アドレスファイルには、 [!DNL Insight Servers] を組織にインストールし、数値 IP アドレスを識別する必要があります。 クライアントは、 [!DNL Insight Server].

クライアントが [!DNL Insight Server]の場合、アドレスファイルを通じてサーバーの共通名の解決を試みます。 アドレスファイルが要求されたサーバの IP アドレスを特定した場合、クライアントは、指定されたアドレスに要求をルーティングします。 アドレスが定義されていない場合（例えば、アドレスファイルでサーバーの共通名が定義されていない場合）、リクエストは失敗します。 必要に応じて、クライアントのアドレスファイルに名前が定義されていない場合は、オペレーティング環境の通常のドメインネーミングサービス (DNS) メカニズムを通じてアドレスを解決するようにクライアントを設定できます。 手順については、 [NetworkLocation パラメータの表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) を参照してください。
