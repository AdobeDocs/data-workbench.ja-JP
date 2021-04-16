---
description: IP Geo-IntelligenceまたはIP Geo-locationルックアップファイルをインストールする手順です。
title: データサービス参照ファイルのインストール
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# データサービス参照ファイルのインストール{#installing-the-data-service-lookup-files}

IP Geo-IntelligenceまたはIP Geo-locationルックアップファイルをインストールする手順です。

データサービスプロファイルに付属のルックアップファイル(Lookups\*プロファイル名*\*データファイル名*)は、IPアドレスに基づく地理的に関連したデータを含むバイナリファイル([!DNL .bin])です。 このファイルを定期的に置き換えて、最新の地理データを使用する必要があります。 「[Data Serviceファイルの更新](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c)」を参照してください。

**IP Geo-IntelligenceまたはIP Geo-Locationルックアップファイルをインストールするには**

>[!NOTE]
>
>すべての[!DNL IP Geo-location]または[!DNL IP Geo-intelligence]データファイルは、Data Workbenchサーバーの使用可能な物理メモリに収まる必要があります。

1. Adobeから受け取った[!DNL .zip]ファイルからLookupsフォルダーを開きます。
1. IP Geo-IntelligenceフォルダーまたはIP Geo-locationフォルダーを、Data WorkbenchサーバーのインストールディレクトリにあるLookupsフォルダーにコピーします(\Lookups\IP Geo-intelligence or a ...\Lookups\IP Geo-location folder on your data workbench server as shown in the following example Lookupsフォルダー内の他のフォルダーの名前は、表示されている名前と異なる場合があります。

   ![ステップ情報](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >定期的に、Adobeから、更新された[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]参照ファイルを含むファイルが送信されます。 これらのファイルを受け取ったら、Adobeの指示に従って、data workbenchサーバーに読み込む必要があります。 手順については、次の節を参照してください。
