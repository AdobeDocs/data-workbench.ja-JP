---
description: Insightサーバーのクライアント（ReportおよびInsight）は、Insightサーバーを表す共通名を使用します。
solution: Insight
title: サーバのネットワークの場所の定義
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# サーバのネットワークの場所の定義{#defining-the-server-s-network-location}

Insightサーバーのクライアント（ReportおよびInsight）は、Insightサーバーを表す共通名を使用します。

例えば、接続時や接続 [!DNL Insight] 時に [!DNL Report] は、サ [!DNL Insight Server]ーバーを共通の名前(例： [!DNL Server.MyCompany.com])で識別します。 クライアントは、サーバーに要求を送信する前に、共通名を数値のIPアドレスに解決します。

共通名をIPアドレスに解決するには、クライアントは [!DNL Insight Server’s] アドレスファイルと呼ばれるローカル参照ファイルを使用します。 アドレスファイルには、組織にインストールされてい [!DNL Insight Servers] るの共通名と、その数値のIPアドレスが表示されます。 クライアントは、上のプロファイルを開くと、アドレスファイルのコピーを自動的に受け取りま [!DNL Insight Server]す。

クライアントは、に対する要求を発 [!DNL Insight Server]行すると、アドレスファイルを通じてサーバーの共通名の解決を試みます。 アドレスファイルが要求されたサーバーのIPアドレスを識別する場合、クライアントは指定されたアドレスに要求をルーティングします。 アドレスが定義されていない場合（例えば、アドレスファイルでサーバーの共通名が定義されていない場合）、要求は失敗します。 オプションで、クライアントのアドレスファイルに名前が定義されていない場合は、オペレーティング環境の通常のドメインネーミングサービス(DNS)メカニズムを通じてアドレスを解決するようにクライアントを設定できます。 手順については、次の節のNetworkLocationパラメーターの表の [Parentパラメーター](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) を参照してください。
