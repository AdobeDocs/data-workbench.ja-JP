---
description: Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。
solution: Analytics
title: 緯度-経度投影法
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 緯度-経度投影法{#latitude-longitude-projections}

Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。

未投影の画像（生の未投影ビットマップおよび未投影の一般的な画像）に対して LatLonProjection を指定するには、data workbench の [!DNL Terrain Images.cfg] ウィンドウ内で LatLonProjection の設定を入力します。See [To specify a LatLonProjection for unprojected images](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

To specify a LatLonProjection for images with embedded projection information, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to “LatLonProjection”, and add settings for the LatLonProjection. See [To specify a LatLonProjection for images within embedded projection information...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [未投影の画像に対してLatLonProjectionを指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [埋め込まれた投影情報内の画像に対してLatLonProjectionを指定するには…](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## To Specify a LatLonProjection for Unprojected Images {#section-26554eefe645481faba68396fa13756a}

1. Data Workbenchでフ [!DNL Terrain Images.cfg] ァイルを開き、地形画像レイヤーを定義するにはの説明に従って、地 [形画像レイヤーソースを追加します](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

1. 以下のパラメーターの表をガイドとして使用して、Projection Info パラメーターを編集します。

   | パラメーター | 説明 |
   |---|---|
   | Lat0 | 画像の上の辺の緯度（度単位）。90 は北極を表し、-90 は南極を表します。 |
   | Lat1 | 画像の下の辺の緯度。 |
   | Lon0 | 画像の左側の辺の経度（度単位）。正数は東経を表し、負数は西経を表します。 |
   | Lon1 | 画像の右側の辺の経度。 |

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. ローカルに適用した変更をData Workbenchサーバーコンピューターに保存するには、 [!DNL Server Files Manager]で、列のチェックマークを右ク [!DNL Terrain Images.cfg] リックし [!DNL Temp] 、 **[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]**>をクリックします*。

## To Specify a LatLonProjection for Images Within Embedded Projection Information {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg].

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] file appears in a Notepad window.

1. 以下のサンプルファイルの一部をガイドとして使用して、Projection Info パラメーターを編集します。以下にハイライトされているように、投影タイプを必ず指定してください。パラメーターの説明については、前の手順の LatLonProjection パラメーターの表を参照してください。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

