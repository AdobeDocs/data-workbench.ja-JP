---
description: Report Portalを設定するには、そのアプリケーションファイルを仮想ディレクトリにマッピングする必要があります。
title: 仮想ディレクトリへの Report Portal ページのマッピング
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# 仮想ディレクトリへの Report Portal ページのマッピング{#map-the-report-portal-pages-to-virtual-directories}

Report Portalを設定するには、そのアプリケーションファイルを仮想ディレクトリにマッピングする必要があります。

仮想ディレクトリは、ブラウザークライアントがIISアプリケーションサーバー上の物理リソースを見つける際に使用するアドレスを定義します。 [!DNL Report Portal]にアクセスするために、クライアントは、ポータルに割り当てた仮想ディレクトリをブラウザーで指し示します。

[!DNL Report Portal]に割り当てる仮想ディレクトリの名前は、前の節の手順3でVSVirtualPortalNameフォルダーに使用した名前と一致する必要があります。 例えば、[!DNL Report Portal]の名前として「Portal」を使用する場合は、ポータルのファイルを「Portal」という名前の仮想ディレクトリにマップする必要があります。 次の例は、クライアントがmyWebServerと呼ばれるサーバー上の仮想ディレクトリ[!DNL VisualReportPortal]に割り当てられた[!DNL Report Portal]にアクセスするために使用するURIを示しています。

[!DNL http://myWebServer/VisualReportPortal]

以下の手順では、IIS 5.0、6.0および7.0以降の仮想ディレクトリに[!DNL Report Portal]をマッピングする方法を説明します。

使用しているIISのバージョンに関する一連の手順に従います。

* [仮想ディレクトリ（IIS 7.0）への Report Portal のマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [セッション設定ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
