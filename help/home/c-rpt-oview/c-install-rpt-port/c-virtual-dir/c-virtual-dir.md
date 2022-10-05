---
description: Report Portal を設定するには、そのアプリケーションファイルを仮想ディレクトリにマッピングする必要があります。
title: 仮想ディレクトリへの Report Portal ページのマッピング
uuid: 75ca85d5-d526-48f9-b2c4-ca77c903c6af
exl-id: 13e457d4-7039-491a-a65d-f23ad7e9fe77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 18%

---

# 仮想ディレクトリへの Report Portal ページのマッピング{#map-the-report-portal-pages-to-virtual-directories}

{{eol}}

Report Portal を設定するには、そのアプリケーションファイルを仮想ディレクトリにマッピングする必要があります。

仮想ディレクトリは、IIS アプリケーションサーバー上の物理リソースを見つけるためにブラウザークライアントが使用するアドレスを定義します。 アクセスするには [!DNL Report Portal]クライアントは、ポータルに割り当てた仮想ディレクトリをブラウザーで参照します。

割り当てる仮想ディレクトリの名前 [!DNL Report Portal] は、前の節の手順 3 で VSVirtualPortalName フォルダに使用した名前と一致する必要があります。 例えば、「Portal」を [!DNL Report Portal]を使用する場合は、ポータルのファイルを「ポータル」という名前の仮想ディレクトリにマッピングする必要があります。 次の例は、クライアントが [!DNL Report Portal] 仮想ディレクトリに割り当てられました [!DNL VisualReportPortal] myWebServer という名前のサーバーで、以下の手順を実行します。

[!DNL https://myWebServer/VisualReportPortal]

次の手順では、 [!DNL Report Portal] を IIS 5.0、6.0、7.0 以降の仮想ディレクトリに追加します。

使用している IIS のバージョンに関する一連の手順に従います。

* [仮想ディレクトリ（IIS 7.0）への Report Portal のマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-7.md#concept-9fc9595bb83147238965be4832df0a08)
* [仮想ディレクトリ（IIS 5.0）への Report Portal のマッピング](../../../../home/c-rpt-oview/c-install-rpt-port/c-virtual-dir/c-map-rpt-port-vdir-5.md#concept-402cb33c50d640e480098517140ffc74)
* \ [セッション設定ファイルの編集](../../../../home/c-rpt-oview/c-install-rpt-port/t-edit-sess-config-file.md#task-cf11c3a780bd4936afd3f64a6b30afc7)
