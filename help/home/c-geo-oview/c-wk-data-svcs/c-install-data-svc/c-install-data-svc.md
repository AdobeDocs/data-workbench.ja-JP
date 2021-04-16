---
description: Data WorkbenchサーバーへのData Serviceのインストールに関する情報です。
title: Data Workbench サーバーへのデータサービスのインストール
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# Data Workbench サーバーへのデータサービスのインストール{#installing-a-data-service-on-a-data-workbench-server}

Data WorkbenchサーバーへのData Serviceのインストールに関する情報です。

IP Geo-IntelligenceデータサービスまたはIP Geo-Locationデータサービスを使用している場合は、[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]プロファイルーと、関連する参照ファイルをData Workbenchサーバーにインストールする必要があります。 Data Workbench [!DNL Geography]プロファイルをインストールした後は、次の手順を実行する必要があります。 [Data Workbench地域のインストール](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)を参照してください。 data workbenchをインストールしていない場合は、次に進む前に、『*Data Workbenchユーザーガイド*』の手順に従ってください。

>[!NOTE]
>
>Data Serviceファイルをインストールするには、Data Workbenchサーバー上のファイルにアクセスできる必要があります。

Adobeは、IP Geo-IntelligenceおよびIP Geo-Locationデータサービスを[!DNL .zip]ファイルとして配布します。 各[!DNL .zip]ファイルには2つのフォルダーが含まれています。検索とプロファイル。 Data WorkbenchサーバーにData Serviceをインストールするには、次の手順を実行する必要があります。

* データサービスプロファイルをインストールします。 「[Data Serviceプロファイルのインストール](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md)」を参照してください。
* データサービス参照をインストールします。 「[Data Service Lookup Filesのインストール](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md)」を参照してください。

データセットプロファイルを処理し実行するData Workbenchサーバーコンピューターに、Data Serviceプロファイルとルックアップファイルをインストールする必要があります。 Data Workbenchサーバークラスターを実行している場合は、マスターサーバーにファイルをインストールする必要があります。 データセットのプロファイルについて詳しくは、『*データセット設定ガイド*』を参照してください。
