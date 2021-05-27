---
description: いずれかのデータサービスを購読する場合、Adobeが提供するデータサービスファイルを定期的に更新する必要があります。
title: データサービスファイルの更新
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 5%

---

# データサービスファイルの更新{#updating-data-service-files}

いずれかのデータサービスを購読する場合、Adobeが提供するデータサービスファイルを定期的に更新する必要があります。

そのためには、Data Workbenchサーバー上のファイルにアクセスできる必要があります。

[!DNL IP Geo-location]または[!DNL IP Geo-intelligence]データファイルを読み込むには、次の手順を実行する必要があります。

## データファイル{#section-2b53c2951ae04c6fa8b3bdf080469ff6}の置き換え

1. Data Workbenchの[!DNL Admin] / [!DNL Dataset and Profile]タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして[!DNL Servers Manager]ワークスペースを開きます。

1. [!DNL Servers Manager]ウィンドウで、ファイルの読み込み先のData Workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。

1. [!DNL Server Files Manager]で、**[!UICONTROL Lookups\IP Geo-location]**&#x200B;または&#x200B;**[!UICONTROL Lookups\IP Geo-intelligence]**&#x200B;の&#x200B;**[!UICONTROL Temp]**&#x200B;列を右クリックし、**[!UICONTROL Open]** / *&lt;**[!UICONTROL folder]***&#x200B;をクリックします。

1. Adobeから提供された[!DNL .bin]データファイルを、 Lookups\IP Geo-locationまたはLookups\IP Geo-intelligenceフォルダーウィンドウにコピーします。
1. データファイルの[!DNL Temp]列を右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]**>*&#x200B;をクリックして、ファイルをData Workbenchサーバーのコンピューターに保存します。

   クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## IPLookup変換{#section-a8b99afe3eb04afabe88e15bd465f935}の更新

1. [!DNL Profile Manager]で、**[!UICONTROL Dataset]**、**[!UICONTROL Transformation]**、**[!UICONTROL Geography]**&#x200B;をクリックします。

1. [!DNL IP Lookup.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しいチェックマークを右クリックし、**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**&#x200B;をクリックします。 変換設定ウィンドウが表示されます。

1. ウィンドウで「**[!UICONTROL Transformation]**」をクリックし、「**[!UICONTROL Transformations]**」をクリックします。

1. **[!UICONTROL IPLookup Quova]**&#x200B;または&#x200B;**[!UICONTROL IPLookup Digital Envoy]**&#x200B;を探してクリックします。

1. FileAdobeーに対して、ファイルの名前を、Fileで指定された新しいデータ([!DNL .bin])ファイルの名前に一致するように更新します。
1. 変換設定ファイルを保存するには、設定ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

1. [!DNL User]列の[!DNL IP Lookup.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL profile name]**>*&#x200B;をクリックして、変更した設定ファイルを、データサービスを使用する各プロファイルに保存します。 データセットプロファイルの同期後、データの再変換が開始されます。

   データセットの再変換について詳しくは、『データセット設定ガイド&#x200B;*』の「再処理と再変換」の章を参照してください。*

   >[!NOTE]
   >
   >Adobeが提供する内部プロファイル（[!DNL IP Geo-location]または[!DNL IP Geo-intelligence]プロファイルを含む）には、変更した設定ファイルを保存しないでください。これらのプロファイルに対する更新をインストールすると、変更内容が上書きされます。

バージョン5.1以降用の[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合は、データサービスのアップデートが完了しています。 ただし、バージョン5.1より前の[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合は、次の追加手順を実行する必要があります。

## ルックアップファイル{#section-ced1efa38a76419d812edd35423dbff7}の置き換え

次の手順は、バージョン5.1より前の[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合にのみ実行してください。

1. [!DNL Server Files Manager]で、**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]**&#x200B;または&#x200B;**[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**&#x200B;をクリックし、**[!UICONTROL Maps]**&#x200B;をクリックしてその内容を表示します。

1. **[!UICONTROL Maps]**&#x200B;の&#x200B;**[!UICONTROL Temp]**&#x200B;列を右クリックし、**[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*&#x200B;をクリックします。

1. Adobeが提供する新しい[!DNL .txt]ファイルを[マップ]フォルダウィンドウにコピーします。
1. [!DNL .txt]ファイルの[!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;をクリックして、ファイルをData Workbenchサーバーのコンピューターに保存します。

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスターData Workbenchサーバーにファイルをアップロードします。

## 画層ファイル{#section-8b84e7099bad40c9a69665a4890fe66e}の更新

>[!NOTE]
>
>次の手順は、バージョン5.1より前の[!DNL IP Geo-intelligence]および[!DNL IP Geo-location]データサービスをインストールした場合にのみ実行してください。

[!DNL IP Geo-intelligence]または[!DNL IP Geo-location]ルックアップ([!DNL .txt])ファイルを参照するすべてのレイヤー([!DNL .layer])ファイルに対して、次の手順を実行します。

1. Data Workbenchサーバーのインストールディレクトリ内のProfiles\*data service name*\Mapsフォルダーにある[!DNL .layer]ファイルをメモ帳などのテキストエディターで開きます。

1. [!DNL Data Paths]ベクトルで、 [!DNL .txt]ルックアップファイルの名前を、次のサンプルファイルでハイライト表示されているように、Adobeから提供される新しい[!DNL .txt]ファイルの名前に一致するように更新します。

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
