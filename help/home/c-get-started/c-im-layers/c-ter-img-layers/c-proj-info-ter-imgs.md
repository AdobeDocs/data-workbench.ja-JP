---
description: data workbench は、すべての地形画像レイヤーソースに対して緯度-経度投影法とユニバーサル横メルカトル（UTM）投影法の両方をサポートしています。
title: 地形画像の投影情報の指定
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 76%

---

# 地形画像の投影情報の指定{#specify-projection-information-for-terrain-images}

data workbench は、すべての地形画像レイヤーソースに対して緯度-経度投影法とユニバーサル横メルカトル（UTM）投影法の両方をサポートしています。

投影情報は、生の未投影ビットマップおよび未投影の一般的な画像に必要です。埋め込み投影情報を使用して画像の投影情報を指定できますが、投影のパラメーターは画像自体に埋め込まれている測地データから自動的に決定されるので、通常その必要はありません。以降の節では、以下の投影形式を [!DNL Terrain Images.cfg] ファイルで指定する方法について詳しく説明します。

## 緯度-経度投影法 {#section-6e335357ec28462ba39c565e0a5986c7}

[!DNL Terrain Images.cfg] ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。

未投影の画像（生の未投影ビットマップおよび未投影の一般的な画像）に対してLatLonProjectionを指定するには、Data Workbenchの[!DNL Terrain Images.cfg]ウィンドウ内でLatLonProjectionの設定を入力します。

埋め込み投影情報を使用して画像の を指定するには、メモ帳などのテキストエディターで [!DNL Terrain Images.cfg] ファイルを開き、Projection Info パラメーターを LatLonProjection に設定し、[!DNL LatLonProjection]LatLonProjection の設定を追加します。

**未投影の画像に対して LatLonProjection を指定するには**

1. Data Workbenchで[!DNL Terrain Images.cfg]ファイルを開き、 [地形画像レイヤー](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)を定義するにはで説明しているように、地形画像レイヤーソースを追加します。
1. 以下のパラメーターの表をガイドとして使用して、Projection Info パラメーターを編集します。

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>画像の上の辺の緯度（度単位）。90 は北極を表し、-90 は南極を表します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>画像の下の辺の緯度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>画像の左側の辺の経度（度単位）。正数は東経を表し、負数は西経を表します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>画像の右側の辺の経度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックして、ファイルを保存します。
1. ローカルで行った変更をData Workbenchサーバーコンピューターに保存するには、[!DNL Server Files Manager]で、[!DNL Temp]列の[!DNL Terrain Images.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;をクリックします。

**埋め込み投影情報を使用して画像の LatLonProjection を指定するには**

[!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

[!DNL Terrain Images.cfg]のサーバー名列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]の[!DNL Temp]列にチェックマークが表示されます。

[!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Notepad]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]ファイルがメモ帳ウィンドウに表示されます。

以下のサンプルファイルの一部をガイドとして使用して、Projection Info パラメーターを編集します。以下にハイライトされているように、投影タイプを必ず指定してください。パラメーターの説明については、前の手順の LatLonProjection パラメーターの表を参照してください。

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## ユニバーサル横メルカトル投影法 {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

ユニバーサル横メルカトル（UTM）投影法は、8 つのパラメーターで定義されます。地形画像レイヤーに対してユニバーサル横メルカトル投影法を指定する場合、地形画像ファイルでは画像の上に偽の（投影された）北を合わせ、画像の右に偽の西を合わせる必要があります。

地形画像ソースに対して UTM 投影法を指定するには、メモ帳などのテキストエディターで [!DNL Terrain Images.cfg] ファイルを開き、Projection Info パラメーターを「TransverseMercatorProjection」に設定し、UTM 投影法の設定を追加する必要があります。

**ユニバーサル横メルカトル投影法を指定するには**

1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。
1. [!DNL Terrain Images.cfg]のサーバー名列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg.]の[!DNL Temp]列にチェックマークが表示されます
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Notepad]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]ファイルがメモ帳ウィンドウに表示されます。
1. 以下のサンプルファイルの一部とパラメーターの表をガイドとして使用して、Projection Info パラメーターを編集します。以下にハイライトされているように、投影タイプを必ず指定してください。

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flattening、Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>投影に使用される楕円のパラメーター。長半径はメートル単位で指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Easting </p> </td> 
   <td colname="col2"> <p>投影の中心子午線の偽の東距（メートル単位）。UTM の場合は常に 500,000 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Northing </p> </td> 
   <td colname="col2"> <p>投影の赤道の偽の北距（メートル単位）。UTM の場合、北半球ゾーンでは 0、南半球ゾーンでは 10,000 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Northwest Corner Coordinates、Southeast Corner Coordinates </p> </td> 
   <td colname="col2"> <p>画像の左上隅と右下隅の座標（投影されたメートル単位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>投影の中心子午線の経度（度単位の東経で指定）。負数を使用して西経の度を指定できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scale Factor </p> </td> 
   <td colname="col2"> <p>楕円の長半径に対する投影円筒の半径の比率。ユニバーサル横メルカトル（UTM）投影法の場合、常に 0.9996 です。 </p> </td> 
  </tr> 
 </tbody> 
</table>
