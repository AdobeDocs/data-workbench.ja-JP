---
description: 1 つ以上のベクトル (.vec) ファイルを参照するベクトルレイヤーを作成できます。このファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。
title: ベクターファイルを参照するベクターレイヤーの定義
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 47%

---

# ベクターファイルを参照するベクターレイヤーの定義{#defining-vector-layers-referencing-vector-files}

{{eol}}

1 つ以上のベクトル (.vec) ファイルを参照するベクトルレイヤーを作成できます。このファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。

1 つ以上の [!DNL .vec]ファイルには、次の設定が必要です。

* 1 つ以上 [!DNL .vec]グローブ上にベクトルを描画するために使用されるデータを含むファイル。

   >[!NOTE]
   >
   >次を取得するには： [!DNL .vec] ベクトルレイヤーで使用するファイル、コンタクトAdobe

* の場所を指定する画層ファイル [!DNL .vec] ファイル。 レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)」を参照してください。

   >[!NOTE]
   >
   >この [!DNL Boundaries.layer] ファイル。 [!DNL Geography] profile は、 [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]、および [!DNL mwisland.vec] ファイル。

## ベクトルレイヤーファイルの形式 {#section-530d03f41ede4a339aebbb680e15240a}

各ベクトルレイヤーファイルの参照 [!DNL .vec]ファイルは、次のテンプレートを使用してフォーマットする必要があります。

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
| Vec Files | へのパス [!DNL .vec] ファイルに含まれています。 |
| Color | RGB カラーベクトルで、(red,green,blue) として表されます。ベクトル内のカラーごとに、0.0 ～ 1.0 の値を入力できます。例えば、(1.0, 0.0, 0.0) は明るい赤で、(0.5, 0.5, 0.5) はグレーです。 |
| Alpha | グローブ上に表示されるベクトルの透明度を制御します。範囲は 0 ～ 1 で、0 が最も透明になります。 |
| Width | （オプション）。データの幅をピクセル単位で設定します。推奨範囲は 1 ～ 4 です。 |
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
