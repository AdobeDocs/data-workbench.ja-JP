---
description: IP Geo-IntelligenceまたはIP Geo-locationルックアップファイルのインストール手順です。
title: データサービス参照ファイルのインストール
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# データサービス参照ファイルのインストール{#installing-the-data-service-lookup-files}

IP Geo-IntelligenceまたはIP Geo-locationルックアップファイルのインストール手順です。

データサービスプロファイルで提供されるルックアップファイル(Lookups\*profile name*\*data file name*)は、IPアドレスに基づいて地理的に関連するデータを含むバイナリファイル([!DNL .bin])です。 このファイルは定期的に置き換え、最新の地理データを取得する必要があります。 [データサービスファイルの更新](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c)を参照してください。

**IP Geo-IntelligenceまたはIP Geo-Locationルックアップファイルをインストールするには**

>[!NOTE]
>
>すべての[!DNL IP Geo-location]データファイルまたは[!DNL IP Geo-intelligence]データファイルは、Data Workbenchサーバーの使用可能な物理メモリに収まっている必要があります。

1. Adobeから受け取った[!DNL .zip]ファイルからLookupsフォルダーを開きます。
1. IP Geo-IntelligenceフォルダーまたはIP Geo-locationフォルダーを、Data Workbenchサーバーのインストールディレクトリ内のLookupsフォルダーにコピーします(\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Lookupsフォルダー内の他のフォルダーの名前は、表示される名前と異なる場合があります。

   ![ステップ情報](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Adobeは、更新された[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]参照ファイルを含むファイルを定期的に送信します。 これらのファイルを受け取ったら、Adobeの指示に従って、Data Workbenchサーバーに読み込む必要があります。 手順については、次の節を参照してください。
