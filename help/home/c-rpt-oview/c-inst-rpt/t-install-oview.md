---
description: Report Serverソフトウェアのインストールと設定の手順です。
solution: Analytics
title: インストールの概要
topic: Data workbench
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# インストールの概要{#installation-overview}

Report Serverソフトウェアのインストールと設定の手順です。

次のタスクは順番に完了する必要があります。

1. Report Serverプログラムファイルをインストールします。
1. Report Serverのデジタル証明書をダウンロードし、インストールします。 See [Downloading and Installing the Digital Certificate](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. Report ServerとData Workbenchサーバー(InsightServer64.exe)の間の接続を設定します。 Insightサー [バーへの接続の設定を参照してください](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)。
1. 言語ファイル（.zbin ファイル）を使用して、Report Server を更新します。

   See [Update Report Server with a language file (.zbin file)](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1.Data Workbenchサーバーコンピューター上のアクセス制御ファイルを更新して、Report ServerがData Workbenchサーバーにアクセスできるようにします。 「Insightサー [バーへのアクセスの有効化」を参照してくださ](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc)い。
1. マスターData Workbenchサーバーコンピューター上の通信ファイルを編集し、インターフェイスにレポートサーバーのステータスを表示 [!DNL Master Server Detailed Status] します。 「レポート [のサーバーステータスを表示するためのInsightサーバーの設定」を参照してくださ](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8)い。
1. レポートをWindowsサービスとして登録します。 「Windowsサー [ビスとしてのレポートの登録」を参照してください](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6)。

