---
description: Report Serverソフトウェアのインストールと設定の手順です。
title: インストールの概要
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# インストールの概要{#installation-overview}

Report Serverソフトウェアのインストールと設定の手順です。

次のタスクは順番に完了する必要があります。

1. Report Serverプログラムファイルをインストールします。
1. Report Serverの電子証明書をダウンロードしてインストールします。 [デジタル証明書のダウンロードとインストール](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)を参照してください。
1. レポートサーバーとData Workbenchサーバー(InsightServer64.exe)間の接続を設定します。 [Insightサーバーへの接続の設定](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)を参照してください。
1. 言語ファイル（.zbin ファイル）を使用して、Report Server を更新します。

   [言語ファイル（.zbinファイル）](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b)を使用したレポートサーバーの更新を参照してください。 1. Data Workbenchサーバーコンピューターのアクセス制御ファイルを更新し、Report ServerがData Workbenchサーバーにアクセスできるようにします。 [Insightサーバーへのアクセスの有効化](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc)を参照してください。
1. マスターData Workbenchサーバーコンピューター上の通信ファイルを編集し、[!DNL Master Server Detailed Status]インターフェイスにレポートサーバーのステータスを表示します。 [レポートのサーバーステータスを表示するためのInsightサーバーの設定](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8)を参照してください。
1. レポートをWindowsサービスとして登録します。 [Windowsサービスとしてのレポートの登録](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6)を参照してください。
