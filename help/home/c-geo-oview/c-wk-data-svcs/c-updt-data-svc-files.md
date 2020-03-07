---
description: いずれかのデータサービスを購読する場合は、アドビが提供するデータサービスファイルを定期的に更新する必要があります。
solution: Analytics
title: データサービスファイルの更新
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データサービスファイルの更新{#updating-data-service-files}

いずれかのデータサービスを購読する場合は、アドビが提供するデータサービスファイルを定期的に更新する必要があります。

これを行うには、Data Workbenchサーバー上のファイルにアクセスできる必要があります。

データファイル [!DNL IP Geo-location] を読み込む [!DNL IP Geo-intelligence] には、次の手順を実行する必要があります。

## データファイルの置換 {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Data Workbenchの「/」タブで、サムネ [!DNL Admin] ールをク [!DNL Dataset and Profile] リックしてワ **[!UICONTROL Servers Manager]** ークスペースを開 [!DNL Servers Manager] きます。

1. ウィンドウ [!DNL Servers Manager] 内で、ファイルを読み込むData Workbenchサーバーのアイコンを右クリックし、をクリックしま **[!UICONTROL Server Files]**&#x200B;す。

1. で、ま [!DNL Server Files Manager]たはの列を右クリックし、/ **[!UICONTROL Temp]****[!UICONTROL Lookups\IP Geo-location]** &lt; **[!UICONTROL Lookups\IP Geo-intelligence]****[!UICONTROL Open]*****[!UICONTROL folder]*** right>をクリックします。

1. アドビから提 [!DNL .bin] 供されたデータファイルを、Lookups\IP Geo-locationまたはLookups\IP Geo-intelligenceフォルダーウィンドウにコピーします。
1. データファイルの列を右クリックし、/ [!DNL Temp] &lt; **[!UICONTROL Save to]** >をクリックして、Data Workbenchサーバーコンピューターにファイルを保存します ***[!UICONTROL server name]***。

   クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## IPLookup変換の更新 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. で、、、 [!DNL Profile Manager]およびを **[!UICONTROL Dataset]**&#x200B;クリ **[!UICONTROL Transformation]**&#x200B;ックしま **[!UICONTROL Geography]**&#x200B;す。

1. の横のチェックマークを右クリックし、をク [!DNL IP Lookup.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しいチェックマークを右クリックし、/をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL from the workbench]**&#x200B;す。 変換設定ウィンドウが表示されます。

1. ウィンドウでをクリックし、 **[!UICONTROL Transformation]**&#x200B;をクリックしま **[!UICONTROL Transformations]**&#x200B;す。

1. またはを探してクリッ **[!UICONTROL IPLookup Quova]** クしま **[!UICONTROL IPLookup Digital Envoy]**&#x200B;す。

1. Fileパラメーターの場合は、ファイルの名前を、アドビが提供する新しいデータ( [!DNL .bin])ファイルの名前と一致するように更新します。
1. 変換設定ファイルを保存します。保存するには、設定ウ **[!UICONTROL (modified)]** ィンドウの上部にある右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

1. 変更した設定ファイルを、列の横のチェックマークを右クリックし、/ [!DNL IP Lookup.cfg] &lt; [!DNL User] >をクリ **[!UICONTROL Save to]** ックして、データサービスを使用する各プ *ロファイルに保存します&#x200B;**[!UICONTROL profile name]***。 データセットプロファイルの同期後、データの再変換が開始されます。

   データセットの再変換について詳しくは、『データセット設定ガイド』の「再処理と再変換」という章を *参照してください*。

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.

バージョン5.1以 [!DNL IP Geo-intelligence] 降のお [!DNL IP Geo-location] よびデータサービスをインストールした場合は、データサービスの更新が完了しています。 ただし、バージョン5.1より前のバ [!DNL IP Geo-intelligence] ージョ [!DNL IP Geo-location] ンでとデータサービスをインストールした場合は、次の追加の手順を実行する必要があります。

## 参照ファイルの置換 {#section-ced1efa38a76419d812edd35423dbff7}

バージョン5.1より前のバージョンとデータサービスをインス [!DNL IP Geo-intelligence] トールし [!DNL IP Geo-location] た場合にのみ、次の手順を実行してください。

1. で、「/」ま [!DNL Server Files Manager]たは「/」をクリ **[!UICONTROL Profiles]** ック **[!UICONTROL IP Geo-intelligence]** し、をクリ **[!UICONTROL Profiles]****[!UICONTROL IP Geo-location]****[!UICONTROL Maps]** ックして内容を表示します。

1. の列を右クリックし、 **[!UICONTROL Temp]** 「>」 **[!UICONTROL Maps]** をク **[!UICONTROL Open]** リック *し&#x200B;**[!UICONTROL folder]**ます*。

1. アドビから提供され [!DNL .txt] た新しいファイルをMapsフォルダーウィンドウにコピーします。
1. ファイルの列のチェックマークを右クリックし、/ [!DNL Temp] &lt; [!DNL .txt] >をクリックして、ファイルをData Workbenchサーバ **[!UICONTROL Save to]** ーコンピューターに *保存し&#x200B;**[!UICONTROL server name]**ます*。

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## レイヤファイルを更新する {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>バージョン5.1より前のバージョンとデータサービスをインス [!DNL IP Geo-intelligence] トールし [!DNL IP Geo-location] た場合にのみ、次の手順を実行してください。

または参照( [!DNL .layer])ファイルを参照するすべてのレイヤ( [!DNL IP Geo-intelligence] )フ [!DNL IP Geo-location] ァイルに [!DNL .txt]対して次の手順を実行します。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*data service name*\Mapsフォルダーにあるメモ帳などのテキス [!DNL .layer] トエディターでファイルを開きます。

1. 次のファ [!DNL Data Paths] イルのサンプルで強調表示されてい [!DNL .txt] るように、ベクトル内で、参照ファイルの名前を、アドビが提供する新し [!DNL .txt] いファイルの名前と一致するように更新します。

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. 更新した画層ファイルを保存します。
1. またはファイルを参照するすべてのファ [!DNL .layer] イルに対して、手順2と3 [!DNL IP Geo-intelligence] を繰り返 [!DNL IP Geo-location][!DNL .txt] します。

