---
description: 1 つ以上のベクトル（.vec）ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。
title: ベクターファイルを参照するベクターレイヤーの定義
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 66%

---

# ベクターファイルを参照するベクターレイヤーの定義{#define-vector-layers-referencing-vector-files}

{{eol}}

1 つ以上のベクトル（.vec）ファイルを参照するベクトルレイヤーを作成できます。ベクトルファイルには、グローブ上に描画するベクトルを定義するデータが格納されています。

1 つ以上の [!DNL .vec] ファイルには、次の設定が必要です。

* **1 つ以上 [!DNL .vec] ファイル** には、グローブ上にベクトルを描くために使用されるデータが格納されています。

   >[!NOTE]
   >
   >次を取得するには： [!DNL .vec] ベクトルレイヤーで使用するファイル、コンタクトAdobe

* **レイヤーファイル** は、 [!DNL .vec] ファイル。 レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1)」を参照してください。

   >[!NOTE]
   >
   >この [!DNL Boundaries.layer] ファイル。 [!DNL Geography] profile は、 [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]、および [!DNL mwisland.vec] ファイル。

## ベクターレイヤーファイル形式 {#section-83a0077cf0c8479b9e7b2939bc761af1}

各ベクトルレイヤーファイルの参照 [!DNL .vec] ファイルは、次のテンプレートを使用してフォーマットする必要があります。

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
