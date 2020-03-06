---
description: レポートポータルを設定するには、そのアプリケーションファイルを仮想ディレクトリにマップする必要があります。
solution: Analytics
title: レポートポータルページの仮想ディレクトリへのマッピング
topic: Data workbench
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートポータルページの仮想ディレクトリへのマッピング{#map-the-report-portal-pages-to-virtual-directories}

レポートポータルを設定するには、そのアプリケーションファイルを仮想ディレクトリにマップする必要があります。

仮想ディレクトリは、ブラウザクライアントがIISアプリケーションサーバー上の物理リソースを見つけるために使用するアドレスを定義します。 クライアント [!DNL Report Portal]は、ポータルに割り当てた仮想ディレクトリをブラウザーが指すようにしてアクセスします。

割り当てる仮想ディレクトリの名前は、前の節の手 [!DNL Report Portal] 順3でVSVirtualPortalNameフォルダに使用した名前と一致する必要があります。 例えば、の名前として「Portal」を使用する場合は、ポータルのファイルを「Portal」とい [!DNL Report Portal]う名前の仮想ディレクトリにマップする必要があります。次の例は、クライアントがmyWebServerというサーバー上の仮想ディレクトリに割り当て [!DNL Report Portal] られたURIにアクセ [!DNL VisualReportPortal] スする際に使用するURIを示しています。

[!DNL http://myWebServer/VisualReportPortal]

次の手順では、IIS 5.0、6.0 [!DNL Report Portal] 、および7.0以降の仮想ディレクトリにマップする方法を説明します。

使用しているIISのバージョンに対する一連の手順に従います。

* [仮想ディレクトリ(IIS 7.0)へのレポートポータルのマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [仮想ディレクトリ(IIS 5.0)へのレポートポータルのマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \セッシ [ョン設定ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)

