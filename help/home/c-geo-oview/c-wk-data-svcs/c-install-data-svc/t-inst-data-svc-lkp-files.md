---
description: IP Geo-Intelligence または IP Geo-location ルックアップファイルのインストール手順です。
title: データサービス参照ファイルのインストール
uuid: a3fe8a14-2c74-4105-bc5b-2298f0f4b61e
exl-id: b19904f4-ead0-4bed-a79f-864c78bc0e1d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 6%

---

# データサービス参照ファイルのインストール{#installing-the-data-service-lookup-files}

{{eol}}

IP Geo-Intelligence または IP Geo-location ルックアップファイルのインストール手順です。

データサービスプロファイルに付属している参照ファイル (Lookups\*profile name*\*data file name*) はバイナリファイル ( [!DNL .bin]) に含まれます。 このファイルは定期的に置き換え、最新の地理データを取得する必要があります。 詳しくは、 [データサービスファイルの更新](../../../../home/c-geo-oview/c-wk-data-svcs/c-updt-data-svc-files.md#concept-2b3d11e4cb814fc09add5de58a87045c).

**IP Geo-Intelligence または IP Geo-Location ルックアップファイルをインストールするには**

>[!NOTE]
>
>すべての [!DNL IP Geo-location] または [!DNL IP Geo-intelligence] データファイルは、data workbench サーバーの使用可能な物理メモリに格納されている必要があります。

1. 次の場所から Lookups フォルダーを開きます。 [!DNL .zip] Adobe
1. IP Geo-intelligence または IP Geo-location フォルダーを、Data Workbench サーバーのインストールディレクトリにある Lookups フォルダーにコピーします (\Lookups\IP Geo-Intelligence または…次の例に示すように、Data Workbench サーバー上の\Lookups\IP Geo-location フォルダーです。 参照フォルダー内の他のフォルダーの名前は、表示される名前と異なる場合があります。

   ![ステップ情報](assets/Geo_installLookups_dirIP.png)

   >[!NOTE]
   >
   >Adobeは、更新された [!DNL IP Geo-intelligence] または [!DNL IP Geo-location] 参照ファイル。 これらのファイルを受け取ったら、Adobeの指示に従って、Data Workbench サーバーに読み込む必要があります。 手順については、次の節を参照してください。
