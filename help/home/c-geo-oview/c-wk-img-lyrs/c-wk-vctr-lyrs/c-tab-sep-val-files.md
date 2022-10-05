---
description: タブ区切り値（.tsv）ファイルを参照するベクトルレイヤーを作成すると、描画手順および経度と緯度のデータを .tsv ファイルから取得することによってベクトルデータが得られます。
title: タブ区切り値ファイルを参照するベクターレイヤー
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 63%

---

# タブ区切り値ファイルを参照するベクターレイヤー{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

タブ区切り値（.tsv）ファイルを参照するベクトルレイヤーを作成すると、描画手順および経度と緯度のデータを .tsv ファイルから取得することによってベクトルデータが得られます。

を参照するベクトルレイヤーを定義するには [!DNL .tsv] ファイルには、次の設定が必要です。

* **A [!DNL .tsv] ファイル** 経度や緯度のデータを含む、グローブ上にベクトルを描くためのデータを含む。 必要な [!DNL .tsv] ファイル： [ベクトル TSV ファイル形式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **レイヤーファイル** は、 [!DNL .tsv] ファイル。 レイヤーファイルの必要な形式について詳しくは、「[ベクトルレイヤーファイルの形式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)」を参照してください。

## ベクトル TSV ファイル形式 {#section-a29012c9ff4444ac8a6d41c68482828e}

この [!DNL .tsv] ファイルには、次の 3 つのタブ区切りの列が含まれている必要があります。

* **[!DNL Begin]:** この列は、新しい行を開始するかどうかを示す必要があります。 この列の値は、0（新しい行を開始しない）か 1（新しい行を開始する）です。
* **[!DNL Longitude]:** この列には、経度の値を含める必要があります。
* **[!DNL Latitude]:** この列には、緯度の値を含める必要があります。

>[!NOTE]
>
>その他の列は無視されます。

以下はサンプルです [!DNL .tsv] ベクトルレイヤーのデータを格納したファイル：

![](assets/tsv_vectorlayer.png)

## ベクターレイヤーファイル形式 {#section-c430923f341f4c93852e9f24b61e82bf}

各ベクトルレイヤーファイルの参照 [!DNL .tsv] ファイルは、次のテンプレートを使用してフォーマットする必要があります。

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
   <td colname="col2"> （オプション）。データの幅をピクセル単位で設定します。推奨範囲は 1 ～ 4 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Factor </td> 
   <td colname="col2"> ベクトルをどれくらい正確に描画するかを制御します。値が大きくなると、ベクトルの描画精度は低下しますが、高速になります。デフォルト値は 5 です。 </td> 
  </tr> 
 </tbody> 
</table>
