---
description: 1つ以上のベクトル(.vec)ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが含まれています。
solution: Analytics
title: ベクトルファイルを参照するベクトルレイヤーの定義
topic: Data workbench
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ベクトルファイルを参照するベクトルレイヤーの定義{#defining-vector-layers-referencing-vector-files}

1つ以上のベクトル(.vec)ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが含まれています。

To define a vector layer that references one or more [!DNL .vec]files, you must have the following:

* One or more [!DNL .vec]files that contain the data used to draw the vectors on the globe.

   >[!NOTE]
   >
   >To obtain [!DNL .vec] files to use with your vector layers, contact Adobe.

* A layer file that specifies the location of the [!DNL .vec] files. レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)」を参照してください。

   >[!NOTE]
   >
   >The [!DNL Boundaries.layer] file, provided with the [!DNL Geography] profile, is a vector layer that references the [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec], and [!DNL mwisland.vec] files.

## ベクトルレイヤーファイルの形式 {#section-530d03f41ede4a339aebbb680e15240a}

Each vector layer file referencing [!DNL .vec]files must be formatted using the following template:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| パラメーター | 説明 |
|---|---|
| Vec Files | Path(s) to the [!DNL .vec] file(s) containing the vector data. |
| Color | RGB カラーベクトルで、(red,green,blue) として表されます。ベクトル内のカラーごとに、0.0 ～ 1.0 の値を入力できます。例えば、(1.0, 0.0, 0.0) は明るい赤で、(0.5, 0.5, 0.5) はグレーです。 |
| Alpha | グローブ上に表示されるベクトルの透明度を制御します。範囲は 0 ～ 1 で、0 が最も透明になります。 |
| Width | (オプション)データの幅をピクセル単位で設定します。推奨範囲は 1 ～ 4 です。 |
| Error Factor | ベクトルをどれくらい正確に描画するかを制御します。値が大きくなると、ベクトルの描画精度は低下しますが、高速になります。デフォルト値は 5 です。 |

[!DNL Boundaries.layer] ファイルは以下のようにフォーマットされています。

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```

