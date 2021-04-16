---
description: データサービスプロファイル（IP Geo-IntelligenceおよびIP Geo-Location）は、Adobeアプリケーションに追加機能を提供する内部プロファイルです。
title: データサービスプロファイルのインストール
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 5%

---

# データサービスプロファイルのインストール{#installing-the-data-service-profile}

データサービスプロファイル（IP Geo-IntelligenceおよびIP Geo-Location）は、Adobeアプリケーションに追加機能を提供する内部プロファイルです。

Adobeが提供する他のすべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

Data Serviceプロファイルーには、Data Workbenchサーバーにインストールされる次のデータセットインクルードファイルが含まれます。

* **プロファイル\*プロファイル名&#x200B;*\Dataset\Log Processing\Traffic\IP.cfg:**は、ログ処理から変換に渡すc-ipフィールドをリストします。
* **プロファイル\*プロファイル名&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**提供されたIP Geo-IntelligenceまたはIP Geo-locationルックアップファイルを使用して、複数のフィールドの地理データを生成するIPLookup変換を定義します。

変換データセットインクルードファイルについて詳しくは、『*データセット設定ガイド*』を参照してください。

また、各データサービスプロファイルは、[!DNL IP Coordinates.layer]という名前の要素ポイントレイヤーファイルを提供します。 このレイヤーファイルを使用すると、IPアドレスを使用してグローブ上のデータセット内の場所を動的にマッピングできます。 インストール後、レイヤーは、data workbenchサーバーのインストールディレクトリ内のプロファイルー\*data service name*\Mapsフォルダーに保存されます。

[!DNL IP Coordinates.layer]ファイルは、座標寸法を参照します。座標寸法は、[!DNL Geography]プロファイルで提供される[!DNL Coordinates.cfg]ファイルで定義され、Dataset\Transformation\Geography folderディレクトリにあります。 データセットに定義されている座標ディメンションの各要素は、その要素に含まれている緯度と経度の情報を使用してグローブ上にマッピングされます。 動的ポイントを使用する要素ポイントレイヤーについて詳しくは、[動的ポイントを使用した要素ポイントレイヤーの定義](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)を参照してください。

>[!NOTE]
>
>バージョン5.1より前のIP Geo-IntelligenceおよびIP Geo-Locationデータサービスをインストールした場合、要素ポイントレイヤーファイルは、動的ポイントを使用する代わりに、参照ファイルを参照します。 各レイヤーファイルは、IP GeocodeルックアップファイルとIP Geocodeディメンションを参照します。 IP Geocodesルックアップファイルには、IP Geocode（IPアドレスに基づく地理的な場所）のリストと、それぞれの緯度と経度が含まれています。 データセットに定義されているIP Geocodeディメンションの各要素は、IP Geocodeルックアップファイルに指定されているそのIP Geocodeの緯度と経度を使用して、グローブ上にマッピングされます。

レイヤーファイルの名前と参照するファイルは、データサービスによって異なります。

* [!DNL IP Geocodes D.layer]ファイルは、IP Geo-Intelligence(Digital Envoy)プロファイルと共にインストールされます。 この要素ポイントレイヤーは、（定期的に更新する必要のある）[!DNL IP Geocodes D yyyymmdd.txt]ルックアップファイルとIP Geocode Dディメンションを参照します。

* [!DNL IP Geocodes Q.layer]ファイルは、IP Geo-Location(Quova)プロファイルと共にインストールされます。 この要素ポイントレイヤーは、（定期的に更新する必要のある）[!DNL IP Geocodes Q yyyymmdd.txt]ルックアップファイルとIP Geocode Qディメンションを参照します。

参照ファイルを使用する要素ポイントレイヤーの詳細については、「[参照ファイルを参照する要素ポイントレイヤーの定義](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)」を参照してください。

## IP Geo-IntelligenceまたはIP Geo-Locationプロファイル{#section-6dff402ffdcb4b31b9bcd0c40a5f7625}をインストールするには

>[!NOTE]
>
>以下のインストール手順は、data workbenchをインストールし、data workbench [!DNL Geography]をインストールするdata workbenchサーバーとdata workbenchサーバーとの接続を確立したことを前提としています。 まだ実行していない場合は、『*Data Workbenchユーザーガイド*』を参照してください。

1. Adobeから受け取った[!DNL .zip]ファイルのプロファイルフォルダーを開きます。
1. IP Geo-IntelligenceフォルダーまたはIP Geo-locationフォルダーを、Data Workbenchサーバーのインストールディレクトリ内のプロファイルフォルダーにコピーします。 最後に…\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example [!DNL Profiles]フォルダー内の他のフォルダーの名前は、表示されている名前と異なる場合があります。

   ![](assets/Geo_installProfiles_dirIP.png)

1. [!DNL IP Geo-intelligence]または[!DNL IP Geo-location]プロファイルを使用する各プロファイルの[!DNL profile.cfg]ファイルを更新するには、次の手順に従います。

   1.  **[!UICONTROL Profile Manager]**.
   1. [!DNL profile.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 [!DNL profile.cfg]ウィンドウが表示されます。

   1. [!DNL profile.cfg]ウィンドウで&#x200B;**[!UICONTROL Directories]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Directory]**&#x200B;をクリックします。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Directory]**&#x200B;をクリックします。

   1. 新しいディレクトリの名前を入力します。[!DNL IP Geo-intelligence]またはI [!DNL P Geo-location]。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL profile.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]**>*&#x200B;をクリックします。

>[!NOTE]
>
>変更した設定ファイルは、Adobeが提供する内部プロファイル([!DNL IP Geo-location]や[!DNL IP Geo-intelligence]プロファイルを含む)には一切保存しないでください。これらのプロファイルに対するアップデートをインストールすると変更内容が上書きされます。
