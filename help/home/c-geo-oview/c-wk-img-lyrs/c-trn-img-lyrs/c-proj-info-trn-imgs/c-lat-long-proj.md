---
description: Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。
title: 緯度-経度投影法
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 50%

---

# 緯度-経度投影法{#latitude-longitude-projections}

Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。

未投影の画像（生の未投影ビットマップおよび未投影の一般的な画像）に対して LatLonProjection を指定するには、data workbench の [!DNL Terrain Images.cfg] ウィンドウ内で LatLonProjection の設定を入力します。[未投影の画像に対してLatLonProjectionを指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)を参照してください。

埋め込み投影情報を含む画像に対してLatLonProjectionを指定するには、メモ帳などのテキストエディターで[!DNL Terrain Images.cfg]ファイルを開き、Projection Infoパラメーターを「LatLonProjection」に設定し、LatLonProjectionの設定を追加する必要があります。 [埋め込み投影情報内の画像に対してLatLonProjectionを指定するにはを参照してください。](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [未投影の画像に対してLatLonProjectionを指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [埋め込み投影情報内の画像に対してLatLonProjectionを指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 未投影の画像に対してLatLonProjectionを指定するには{#section-26554eefe645481faba68396fa13756a}

1. data workbenchで[!DNL Terrain Images.cfg]ファイルを開き、[地形画像レイヤーを定義するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)の説明に従って、地形画像レイヤーソースを追加します。

1. 以下のパラメーターの表をガイドとして使用して、Projection Info パラメーターを編集します。

   | パラメーター | 説明 |
   |---|---|
   | Lat0 | 画像の上の辺の緯度（度単位）。90 は北極を表し、-90 は南極を表します。 |
   | Lat1 | 画像の下の辺の緯度。 |
   | Lon0 | 画像の左側の辺の経度（度単位）。正数は東経を表し、負数は西経を表します。 |
   | Lon1 | 画像の右側の辺の経度。 |

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックして、ファイルを保存します。

1. ローカルに適用した変更をData Workbenchサーバーコンピューターに保存するには、[!DNL Server Files Manager]で、[!DNL Temp]列の[!DNL Terrain Images.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;をクリックします。

## 埋め込み投影情報内の画像に対してLatLonProjectionを指定するには{#section-174f4e00fad84a7ca0c995423dd37ae1}

1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components]**&#x200B;をクリックして、内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

1. [!DNL Terrain Images.cfg]のサーバー名列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]の[!DNL Temp]列にチェックマークが表示されます。

1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]ファイルがメモ帳ウィンドウに表示されます。

1. 以下のサンプルファイルの一部をガイドとして使用して、Projection Info パラメーターを編集します。以下にハイライトされているように、投影タイプを必ず指定してください。パラメーターの説明については、前の手順の LatLonProjection パラメーターの表を参照してください。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
