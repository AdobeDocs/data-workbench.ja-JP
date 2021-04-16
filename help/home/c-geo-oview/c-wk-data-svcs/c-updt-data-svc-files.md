---
description: いずれかのデータサービスをサブスクライブする場合は、Adobeが提供するデータサービスファイルを定期的に更新する必要があります。
title: データサービスファイルの更新
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 5%

---

# データサービスファイルの更新{#updating-data-service-files}

いずれかのデータサービスをサブスクライブする場合は、Adobeが提供するデータサービスファイルを定期的に更新する必要があります。

そのためには、Data Workbenchサーバー上のファイルにアクセスできる必要があります。

[!DNL IP Geo-location]または[!DNL IP Geo-intelligence]データファイルを読み込むには、次の手順を実行する必要があります。

## データファイルの置き換え{#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Data Workbenchの「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして[!DNL Servers Manager]ワークスペースを開きます。

1. [!DNL Servers Manager]ウィンドウ内で、ファイルの読み込み先のdata workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。

1. [!DNL Server Files Manager]で、**[!UICONTROL Lookups\IP Geo-location]**&#x200B;または&#x200B;**[!UICONTROL Lookups\IP Geo-intelligence]**&#x200B;の&#x200B;**[!UICONTROL Temp]**&#x200B;列を右クリックし、**[!UICONTROL Open]**/***[!UICONTROL folder]**>*&#x200B;をクリックします。

1. Adobeから提供された[!DNL .bin]データファイルをLookups\IP Geo-locationまたはLookups\IP Geo-intelligenceフォルダーウィンドウにコピーします。
1. データファイルの[!DNL Temp]列を右クリックし、**[!UICONTROL Save to]**/*&lt;**[!UICONTROL server name]**>*&#x200B;をクリックして、Data Workbenchサーバーコンピューターにファイルを保存します。

   クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## IPLookup変換の更新{#section-a8b99afe3eb04afabe88e15bd465f935}

1. [!DNL Profile Manager]で、**[!UICONTROL Dataset]**、**[!UICONTROL Transformation]**、**[!UICONTROL Geography]**&#x200B;の順にクリックします。

1. [!DNL IP Lookup.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しいチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 変換設定ウィンドウが表示されます。

1. ウィンドウで&#x200B;**[!UICONTROL Transformation]**&#x200B;をクリックし、**[!UICONTROL Transformations]**&#x200B;をクリックします。

1. **[!UICONTROL IPLookup Quova]**&#x200B;または&#x200B;**[!UICONTROL IPLookup Digital Envoy]**&#x200B;を探してクリックします。

1. Fileパラメーターの場合は、ファイル名を、Adobeが提供する新しいデータ([!DNL .bin])ファイルの名前と一致するように更新します。
1. 設定ウィンドウの上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックして、変換設定ファイルを保存します。

1. [!DNL User]列の[!DNL IP Lookup.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL profile name]**>*&#x200B;をクリックして、変更した設定ファイルを、データサービスを使用する各プロファイルに保存します。 データセットプロファイルの同期後、データの再変換が開始されます。

   データセットの再変換について詳しくは、『データセット設定ガイド&#x200B;*』の「再処理と再変換」という章を参照してください。*

   >[!NOTE]
   >
   >変更した設定ファイルは、Adobeが提供する内部プロファイル([!DNL IP Geo-location]や[!DNL IP Geo-intelligence]プロファイルを含む)には一切保存しないでください。これらのプロファイルに対するアップデートをインストールすると変更内容が上書きされます。

バージョン5.1以降用の[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合は、データサービスの更新が完了しています。 ただし、バージョン5.1より前のバージョン[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合は、次の追加の手順を実行する必要があります。

## 参照ファイルの置き換え{#section-ced1efa38a76419d812edd35423dbff7}

バージョン5.1より前のバージョン[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合にのみ、次の手順を実行してください。

1. [!DNL Server Files Manager]で、**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]**&#x200B;または&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**&#x200B;のいずれかをクリックし、**[!UICONTROL Maps]**&#x200B;をクリックしてその内容を表示します。

1. **[!UICONTROL Maps]**&#x200B;の&#x200B;**[!UICONTROL Temp]**&#x200B;列を右クリックし、**[!UICONTROL Open]**/***[!UICONTROL folder]**>*&#x200B;をクリックします。

1. Adobeが提供する新しい[!DNL .txt]ファイルをMapsフォルダウィンドウにコピーします。
1. [!DNL .txt]ファイルの[!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]**>*&#x200B;をクリックして、ファイルをData Workbenchサーバーコンピューターに保存します。

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## レイヤーファイルの更新{#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>バージョン5.1より前のバージョン[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合にのみ、次の手順を実行してください。

[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]参照([!DNL .txt])ファイルを参照するすべてのレイヤー([!DNL .layer])ファイルに対して、次の手順を実行します。

1. Data Workbenchサーバーのインストールディレクトリ内のプロファイル\*Data Service name*\Mapsフォルダーにある[!DNL .layer]ファイルをメモ帳などのテキストエディターで開きます。

1. [!DNL Data Paths]ベクトル内で、[!DNL .txt]ルックアップファイルの名前を、Adobeが提供する新しい[!DNL .txt]ファイルの名前と一致するように更新します。次のファイル例を参照してください。

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
1. [!DNL IP Geo-intelligence]または[!DNL IP Geo-location] [!DNL .txt]ファイルを参照する[!DNL .layer]ファイルごとに手順2と3を繰り返します。
