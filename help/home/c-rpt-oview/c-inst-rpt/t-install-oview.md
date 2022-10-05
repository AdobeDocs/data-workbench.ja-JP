---
description: Report Server ソフトウェアのインストールと設定の手順です。
title: インストールの概要
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 8%

---

# インストールの概要{#installation-overview}

{{eol}}

Report Server ソフトウェアのインストールと設定の手順です。

次のタスクは、順番に実行する必要があります。

1. Report Server プログラムファイルをインストールします。
1. Report Server の電子証明書をダウンロードしてインストールします。 詳しくは、 [電子証明書のダウンロードとインストール](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
1. レポートサーバーと Data Workbench サーバー (InsightServer64.exe) 間の接続を設定します。 詳しくは、 [Insight サーバーへの接続の設定](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c).
1. 言語ファイル（.zbin ファイル）を使用して、Report Server を更新します。

   詳しくは、 [言語ファイル（.zbin ファイル）を使用したレポートサーバーの更新](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b). 1. Data Workbench サーバーマシン上のアクセス制御ファイルを更新し、Report Server が Data Workbench サーバーにアクセスできるようにします。 詳しくは、 [Insight サーバーへのアクセスの有効化](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc).
1. マスター Data Workbench サーバーコンピューター上の通信ファイルを編集し、 [!DNL Master Server Detailed Status] インターフェイス。 詳しくは、 [レポートのサーバーステータスを表示するための Insight サーバーの設定](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8).
1. レポートを Windows サービスとして登録します。 詳しくは、 [Windows サービスとしてのレポートの登録](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6).
