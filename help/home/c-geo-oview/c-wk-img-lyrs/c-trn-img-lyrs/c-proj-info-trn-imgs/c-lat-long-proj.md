---
description: Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。
title: 緯度-経度投影法
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 50%

---

# 緯度-経度投影法{#latitude-longitude-projections}

{{eol}}

Terrain Images.cfg ファイル内の緯度-経度投影形式（LatLonProjection）は、緯度と経度に関する 4 つのパラメーターで定義されます。

未投影の画像（生の未投影ビットマップおよび未投影の一般的な画像）に対して LatLonProjection を指定するには、data workbench の [!DNL Terrain Images.cfg] ウィンドウ内で LatLonProjection の設定を入力します。詳しくは、 [未投影の画像に対して LatLonProjection を指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

埋め込まれた投影情報を含む画像に対して LatLonProjection を指定するには、 [!DNL Terrain Images.cfg] ファイルをメモ帳などのテキストエディターで、Projection Info パラメーターを「LatLonProjection」に設定し、LatLonProjection の設定を追加します。 詳しくは、 [埋め込み投影情報内の画像に対して LatLonProjection を指定するには…](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [未投影の画像に対して LatLonProjection を指定するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [埋め込み投影情報内の画像に対して LatLonProjection を指定するには…](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 未投影の画像に対して LatLonProjection を指定するには {#section-26554eefe645481faba68396fa13756a}

1. を開きます。 [!DNL Terrain Images.cfg] data workbench のファイルを編集し、 [地形画像レイヤーを定義するには](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. 以下のパラメーターの表をガイドとして使用して、Projection Info パラメーターを編集します。

   | パラメーター | 説明 |
   |---|---|
   | Lat0 | 画像の上の辺の緯度（度単位）。90 は北極を表し、-90 は南極を表します。 |
   | Lat1 | 画像の下の辺の緯度。 |
   | Lon0 | 画像の左側の辺の経度（度単位）。正数は東経を表し、負数は西経を表します。 |
   | Lon1 | 画像の右側の辺の経度。 |

1. 右クリックしてファイルを保存 **[!UICONTROL (modified)]** をクリックし、 **[!UICONTROL Save]**.

1. ローカルで行った変更を Data Workbench サーバーコンピューターに保存するには、 [!DNL Server Files Manager]、次のチェックマークを右クリック： [!DNL Terrain Images.cfg] 内 [!DNL Temp] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 埋め込み投影情報内の画像に対して LatLonProjection を指定するには {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

1. 次のサーバー名列のチェックマークを右クリック [!DNL Terrain Images.cfg]を選択し、「 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Terrain Images.cfg].

1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. この [!DNL Terrain Images.cfg] ファイルがメモ帳ウィンドウに表示されます。

1. 以下のサンプルファイルの一部をガイドとして使用して、Projection Info パラメーターを編集します。以下にハイライトされているように、投影タイプを必ず指定してください。パラメーターの説明については、前の手順の LatLonProjection パラメーターの表を参照してください。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
