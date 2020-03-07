---
description: IP Geo-IntelligenceまたはIP Geo-Location参照ファイルをインストールする手順です。
solution: Analytics
title: Data Service Lookupファイルのインストール
topic: Data workbench
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Service Lookupファイルのインストール{#installing-the-data-service-lookup-files}

IP Geo-IntelligenceまたはIP Geo-Location参照ファイルをインストールする手順です。

データサービスプロファイルと共に提供される参照ファイル(Lookups\*profile name*\*data file name*)は、IPアドレスに基づいて地理的に関連するデータを含むバイナリファイル( [!DNL .bin])です。 このファイルを定期的に置き換えて、最新の地理データを確実に取得する必要があります。 Updating Data [Service Filesを参照してください](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c)。

**IP Geo-IntelligenceまたはIP Geo-Location参照ファイルをインストールするには**

>[!NOTE]
>
>すべてのまたはデ [!DNL IP Geo-location] ータフ [!DNL IP Geo-intelligence] ァイルは、Data Workbenchサーバーの使用可能な物理メモリに収まる必要があります。

1. アドビから受け取ったファイル [!DNL .zip] からLookupsフォルダーを開きます。
1. IP Geo-IntelligenceまたはIP Geo-Locationフォルダーを、Data Workbenchサーバーのインストールディレクトリ内のLookupsフォルダーにコピーします(最後に…\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example. Lookupsフォルダー内の他のフォルダーの名前は、表示されている名前と異なる場合があります。

   ![ステップ情報](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >アドビからは、更新されたファイルまたは参照ファイルを含むファ [!DNL IP Geo-intelligence] イルが定期的 [!DNL IP Geo-location] に送信されます。 これらのファイルを受け取ったら、アドビの指示に従って、Data Workbenchサーバーに読み込む必要があります。 手順については、次の節を参照してください。

