---
description: いずれかのデータサービスを購読する場合、Data Service が提供するデータサービスファイルを定期的に更新する必要があります。Adobe
title: データサービスファイルの更新
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 5%

---

# データサービスファイルの更新{#updating-data-service-files}

{{eol}}

いずれかのデータサービスを購読する場合、Data Service が提供するデータサービスファイルを定期的に更新する必要があります。Adobe

そのためには、Data Workbench サーバー上のファイルにアクセスできる必要があります。

読み込む [!DNL IP Geo-location] または [!DNL IP Geo-intelligence] データファイルを使用する場合は、次の手順を実行する必要があります。

## データファイルの置き換え {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. Data Workbench で、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを開く [!DNL Servers Manager] ワークスペース。

1. 内 [!DNL Servers Manager] ウィンドウで、ファイルの読み込み先の data workbench サーバーのアイコンを右クリックし、 **[!UICONTROL Server Files]**.

1. 内 [!DNL Server Files Manager]、 **[!UICONTROL Temp]** 列 **[!UICONTROL Lookups\IP Geo-location]** または **[!UICONTROL Lookups\IP Geo-intelligence]** をクリックし、 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. を [!DNL .bin] Adobeが Lookups\IP Geo-location または Lookups\IP Geo-intelligence フォルダーウィンドウに提供するデータファイル。
1. ファイルを Data Workbench サーバーコンピューターに保存するには、 [!DNL Temp] 列をクリックし、 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   クラスターを実行している場合は、クラスター内のマスター Data Workbench サーバーにファイルをアップロードします。

## IPLookup 変換の更新 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**、および **[!UICONTROL Geography]**.

1. の横のチェックマークを右クリックします。 [!DNL IP Lookup.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。

1. 新しいチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 変換設定ウィンドウが表示されます。

1. ウィンドウで、 **[!UICONTROL Transformation]**&#x200B;を選択し、「 **[!UICONTROL Transformations]**.

1. を探して、次のいずれかをクリックします。 **[!UICONTROL IPLookup Quova]** または **[!UICONTROL IPLookup Digital Envoy]**.

1. File パラメーターで、新しいデータの名前 ( [!DNL .bin]) ファイルに関する情報は、Adobeが提供します。
1. 右クリックして変換設定ファイルを保存します **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**.

1. 変更した設定ファイルを、データサービスを使用する各プロファイルに保存するには、の横のチェックマークを右クリックします。 [!DNL IP Lookup.cfg] 内 [!DNL User] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. データセットプロファイルの同期後、データの再変換が開始されます。

   データセットの再変換について詳しくは、 *データセット設定ガイド*.

   >[!NOTE]
   >
   >変更した設定ファイルを、Adobeが提供する内部プロファイル ( [!DNL IP Geo-location] または [!DNL IP Geo-intelligence] プロファイル )。変更内容は、これらのプロファイルの更新をインストールすると上書きされます。

をインストールした場合、 [!DNL IP Geo-intelligence] および [!DNL IP Geo-location] バージョン 5.1 以降のデータサービスで、データサービスの更新を完了しています。 ただし、 [!DNL IP Geo-intelligence] および [!DNL IP Geo-location] バージョン 5.1 より前のデータサービスでは、次の追加の手順を実行する必要があります。

## 参照ファイルの置き換え {#section-ced1efa38a76419d812edd35423dbff7}

次の手順は、 [!DNL IP Geo-intelligence] および [!DNL IP Geo-location] バージョン 5.1 より前のデータサービス。

1. 内 [!DNL Server Files Manager]をクリックします。 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** または **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**&#x200B;を選択し、「 **[!UICONTROL Maps]** をクリックして、その内容を表示します。

1. を右クリックします。 **[!UICONTROL Temp]** 列 **[!UICONTROL Maps]** をクリックし、 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. 新しい [!DNL .txt] [ マップ ] フォルダウィンドウにAdobeで提供されるファイル。
1. ファイルを Data Workbench サーバーコンピューターに保存するには、 [!DNL Temp] 列 [!DNL .txt] ファイルとクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスター Data Workbench サーバーにファイルをアップロードします。

## レイヤーファイルを更新する {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>次の手順は、 [!DNL IP Geo-intelligence] および [!DNL IP Geo-location] バージョン 5.1 より前のデータサービス。

各レイヤーに対して次の手順を実行します ( [!DNL .layer]) ファイルを参照します。 [!DNL IP Geo-intelligence] または [!DNL IP Geo-location] 参照 ( [!DNL .txt]) ファイルです。

1. Data Workbench サーバーのインストールディレクトリ内の Profiles\*Data Service name*\Maps フォルダーで、 [!DNL .layer] ファイルをメモ帳などのテキストエディターで作成します。

1. 内 [!DNL Data Paths] ベクトルを更新する場合は、 [!DNL .txt] 新しい [!DNL .txt] 次のファイル例でハイライト表示されているように、Adobeによって提供されるファイル。

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
1. 手順 2 と 3 を [!DNL .layer] を参照するファイル [!DNL IP Geo-intelligence] または [!DNL IP Geo-location] [!DNL .txt] ファイル。
