---
description: タブ区切り値（.tsv）ファイルを参照するベクトルレイヤーを作成すると、描画手順および経度と緯度のデータを .tsv ファイルから取得することによってベクトルデータが得られます。
solution: Analytics
title: タブ区切り値ファイルを参照するベクトルレイヤー
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Vector layers referencing tab separated values files{#vector-layers-referencing-tab-separated-values-files}

タブ区切り値（.tsv）ファイルを参照するベクトルレイヤーを作成すると、描画手順および経度と緯度のデータを .tsv ファイルから取得することによってベクトルデータが得られます。

To define a vector layer that references a [!DNL .tsv] files, you must have the following:

* **経度[!DNL .tsv]と緯度** のデータを含む、グローブ上のベクトルの描画に使用されるデータを含むファイルです。 For more information about the required format of the [!DNL .tsv] file, see [Vector TSV File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **ファイルの場所** を指定するレイヤーファ [!DNL .tsv] イル。 レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)」を参照してください。

## Vector TSV file format {#section-a29012c9ff4444ac8a6d41c68482828e}

The [!DNL .tsv] file must contain the following three tab separated columns:

* **[!DNL Begin]:**この列は、新しい行を開始するかどうかを示す必要があります。 この列の値は、0（新しい行を開始しない）か 1（新しい行を開始する）です。
* **[!DNL Longitude]:**この列には、経度の値を含める必要があります。
* **[!DNL Latitude]:**この列には緯度の値を含める必要があります。

>[!NOTE]
>
>列を追加しても無視されます。

Following is a sample [!DNL .tsv] file that contains data for a vector layer:

![](assets/tsv_vectorlayer.png)

## Vector layer file format {#section-c430923f341f4c93852e9f24b61e82bf}

Each vector layer file referencing [!DNL .tsv] files must be formatted using the following template:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV Files </td> 
   <td colname="col2"> <p>ベクトルデータを含む <span class="filepath">.tsv</span> ファイルへのパス。 </p> <p>例：<span class="filepath">Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> RGB カラーベクトルで、(red,green,blue) として表されます。ベクトル内のカラーごとに、0.0 ～ 1.0 の値を入力できます。例えば、(1.0, 0.0, 0.0) は明るい赤で、(0.5, 0.5, 0.5) はグレーです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> グローブ上に表示されるベクトルの透明度を制御します。範囲は 0 ～ 1 で、0 が最も透明になります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Width </td> 
   <td colname="col2"> (オプション)データの幅をピクセル単位で設定します。推奨範囲は 1 ～ 4 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Factor </td> 
   <td colname="col2"> ベクトルをどれくらい正確に描画するかを制御します。値が大きくなると、ベクトルの描画精度は低下しますが、高速になります。デフォルト値は 5 です。 </td> 
  </tr> 
 </tbody> 
</table>

