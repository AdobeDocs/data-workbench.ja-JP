---
description: 1 つ以上のベクトル（.vec）ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。
solution: Analytics
title: ベクトルファイルを参照するベクトルレイヤーの定義
topic: Data workbench
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Define vector layers referencing vector files{#define-vector-layers-referencing-vector-files}

1 つ以上のベクトル（.vec）ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。

To define a vector layer that references one or more [!DNL .vec] files, you must have the following:

* **グローブ上にベク[!DNL .vec]トルを描画** するために使用されるデータを含む1つ以上のファイル。

   >[!NOTE]
   >
   >To obtain [!DNL .vec] files to use with your vector layers, contact Adobe.

* **ファイルの場所** を指定するレイヤーファ [!DNL .vec] イル。 レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1)」を参照してください。

   >[!NOTE]
   >
   >The [!DNL Boundaries.layer] file, provided with the [!DNL Geography] profile, is a vector layer that references the [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec], and [!DNL mwisland.vec] files.

## Vector layer file format {#section-83a0077cf0c8479b9e7b2939bc761af1}

Each vector layer file referencing [!DNL .vec] files must be formatted using the following template:

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

