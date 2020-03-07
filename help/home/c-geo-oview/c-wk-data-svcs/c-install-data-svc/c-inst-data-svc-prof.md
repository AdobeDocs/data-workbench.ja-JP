---
description: データサービスプロファイル（IP Geo-IntelligenceおよびIP Geo-Location）は、アドビのアプリケーションに追加機能を提供する内部プロファイルです。
solution: Analytics
title: Data Service Profileのインストール
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Service Profileのインストール{#installing-the-data-service-profile}

データサービスプロファイル（IP Geo-IntelligenceおよびIP Geo-Location）は、アドビのアプリケーションに追加機能を提供する内部プロファイルです。

アドビが提供する他のすべての内部プロファイルと同様に、これらのプロファイルは変更しないでください。 すべてのカスタマイズは、お客様のデータセットまたはお客様が作成する役割に特有のプロファイルまたはその他のプロファイルで行う必要があります。

データサービスプロファイルには、Data Workbenchサーバーにインストールされる次のデータセットインクルードファイルが含まれます。

* **Profiles\*profile name *\Dataset\Log Processing\Traffic\IP.cfg:**ログ処理から変換に渡すc-ipフィールドを表示します。
* **Profiles\*profile name *\Dataset\Transformation\Geography\IPLookup.cfg:**提供されたIP Geo-IntelligenceまたはIP Geo-locationルックアップファイルを使用して、複数の地理データフィールドを生成するIPLookup変換を定義します。

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

さらに、各データサービスプロファイルには、という名前の要素ポイントレイヤーファイルが用意されていま [!DNL IP Coordinates.layer]す。 このレイヤーファイルを使用すると、IPアドレスを使用して、グローブ上のデータセット内の場所を動的にマッピングできます。 インストール後、レイヤーはData Workbenchサーバーのインストールディレクトリ内のProfiles\*data service name*\Mapsフォルダーに保存されます。

このフ [!DNL IP Coordinates.layer] ァイルは、座標ディメンションを参照します。座標ディメンションは、プロフ [!DNL Coordinates.cfg] ァイルと共に提供され、 [!DNL Geography] Dataset\Transformation\Geography folderフォルダーに格納されているファイルで定義されます。 データセットに定義された座標ディメンションの各要素は、その要素に含まれる緯度と経度の情報を使用してグローブ上にマッピングされます。 動的ポイントを使用する要素ポイントレイヤーの詳細については、「動的ポイントを使用した要 [素ポイントレイヤーの定義」を参照してください](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>バージョン5.1より前のIP Geo-IntelligenceおよびIP Geo-Locationデータサービスをインストールした場合、要素ポイントレイヤーファイルは、動的ポイントを使用する代わりに参照ファイルを参照します。 各レイヤーファイルは、IP GeocodeルックアップファイルとIP Geocodeディメンションを参照します。 IP Geocodes参照ファイルには、IP Geocode（IPアドレスに基づく地理的な場所）と、各地域の緯度と経度のリストが含まれています。 データセットに定義されたIP Geocodeディメンションの各要素は、IP GeocodesルックアップファイルでそのIP Geocodeに対してリストされている緯度と経度を使用して、グローブ上にマッピングされます。

レイヤーファイルの名前と参照するファイルは、データサービスによって異なります。

* このフ [!DNL IP Geocodes D.layer] ァイルは、IP Geo-Intelligence(Digital Envoy)プロファイルと共にインストールされます。 この要素ポイントレイヤーは、(定 [!DNL IP Geocodes D yyyymmdd.txt] 期的に更新する必要のある)参照ファイルとIP Geocode Dディメンションを参照します。

* このフ [!DNL IP Geocodes Q.layer] ァイルは、IP Geo-location(Quova)プロファイルと共にインストールされます。 この要素ポイントレイヤーは、(定 [!DNL IP Geocodes Q yyyymmdd.txt] 期的に更新する必要のある)参照ファイルとIP Geocode Qディメンションを参照します。

参照ファイルを使用する要素ポイントレイヤーの詳細については、「要素ポイントレイヤーの定義」「参 [照ファイルの参照」を参照してくださ](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)い。

## IP Geo-IntelligenceまたはIP Geo-Locationプロファイルをインストールするには {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>次のインストール手順は、Data Workbenchをインストールし、Data WorkbenchをインストールするData Workbenchサーバーとの接続を確立したことを前提としていま [!DNL Geography]す。 まだ実行していない場合は、『 *Data Workbenchユーザーガイド』を参照してください*。

1. アドビから受け取ったファイル [!DNL .zip] のProfilesフォルダーを開きます。
1. IP Geo-IntelligenceまたはIP Geo-Locationフォルダーを、Data Workbenchサーバーのインストールディレクトリ内のProfilesフォルダーにコピーします。 最後に…\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. フォルダ内の他のフォルダの名前は、表示さ [!DNL Profiles] れているものと異なる場合があります。

   ![](assets/Geo_installProfiles_dirIP.png)

1. またはプロファイルを使用する各 [!DNL profile.cfg] プロファイルのファイルを更新するには、次の手順を [!DNL IP Geo-intelligence] 実行し [!DNL IP Geo-location] ます。

   1.  **[!UICONTROL Profile Manager]**.
   1. の横のチェックマークを右クリックし、をク [!DNL profile.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

   1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。 The [!DNL profile.cfg] window appears.

   1. ウィンドウ [!DNL profile.cfg]で右クリックし、「>」 **[!UICONTROL Directories]** をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

      新しいディレクトリをディレクトリのリストの最後に追加するには、リスト内の最後のディレクトリの番号または名前を右クリックし、/をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Directory]**&#x200B;す。

   1. 新しいディレクトリの名前を入力します。あ [!DNL IP Geo-intelligence] るいは [!DNL P Geo-location]私

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL profile.cfg] ックし [!DNL User] 、/ **[!UICONTROL Save to]** &lt; *>をクリック&#x200B;**[!UICONTROL profile name]**します*。

>[!NOTE]
>
>Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.

