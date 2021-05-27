---
description: ユニバーサル横メルカトル（UTM）投影法は、8 つのパラメーターで定義されます。
title: ユニバーサル横メルカトル投影法
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 86%

---

# ユニバーサル横メルカトル投影法{#universal-transverse-mercator-projections}

ユニバーサル横メルカトル（UTM）投影法は、8 つのパラメーターで定義されます。

地形画像レイヤーに対してユニバーサル横メルカトル投影法を指定する場合、地形画像ファイルでは画像の上に偽の（投影された）北を合わせ、画像の右に偽の西を合わせる必要があります。

地形画像ソースに対して UTM 投影法を指定するには、メモ帳などのテキストエディターで [!DNL Terrain Images.cfg] ファイルを開き、Projection Info パラメーターを「TransverseMercatorProjection」に設定し、UTM 投影法の設定を追加する必要があります。

**ユニバーサル横メルカトル投影法を指定するには**

1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

1. *[!DNL Terrain Images.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]の[!DNL Temp]列にチェックマークが表示されます。

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

| パラメーター | 説明 |
|---|---|
| Ellipsoid Inverse Flattening、Ellipsoid Semimajor Axis | 投影に使用される楕円のパラメーター。長半径はメートル単位で指定します。 |
| False Easting | 投影の中心子午線の偽の東距（メートル単位）。UTM の場合は常に 500,000 です。 |
| False Northing | 投影の赤道の偽の北距（メートル単位）。UTM の場合、北半球ゾーンでは 0、南半球ゾーンでは 10,000 です。 |
| Northwest Corner Coordinates、Southeast Corner Coordinates | 画像の左上隅と右下隅の座標（投影されたメートル単位）。 |
| Prime Meridian | 投影の中心子午線の経度（度単位の東経で指定）。負数を使用して西経の度を指定できます。 |
| Scale Factor | 楕円の長半径に対する投影円筒の半径の比率。ユニバーサル横メルカトル（UTM）投影法の場合、常に 0.9996 です。 |
