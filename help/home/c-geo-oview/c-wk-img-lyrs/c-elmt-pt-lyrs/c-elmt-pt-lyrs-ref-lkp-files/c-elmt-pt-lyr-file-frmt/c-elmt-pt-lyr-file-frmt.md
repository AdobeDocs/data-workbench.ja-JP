---
description: 要素ポイントレイヤーファイルに関する情報の形式設定
title: 要素ポイントレイヤーファイルの形式
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 92%

---

# 要素ポイントレイヤーファイルの形式{#element-point-layer-file-format}

要素ポイントレイヤーファイルに関する情報の形式設定

参照ファイルを参照する各要素ポイントレイヤー[!DNL .layer]ファイルは、次のテンプレートを使用してフォーマットする必要があります。

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Paths </td> 
   <td colname="col2"> 緯度と経度のデータを含む参照ファイルへのパス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude Column </td> 
   <td colname="col2"> 経度データを含む参照ファイルの列の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude Column </td> 
   <td colname="col2"> 緯度データを含む参照ファイルの列の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name Column </td> 
   <td colname="col2"> （オプション）緯度と経度のデータで表される位置の名前を含む参照ファイルの列の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Key Column </td> 
   <td colname="col2"> <p>共通キーデータを含む参照ファイル内の列の名前。data workbench サーバーが参照ファイル内のデータをデータセットに統合できるようにします。この列は、参照ファイル内の先頭列でなければなりません。 </p> <p>この列の各行は、ディメンションの要素です。このディメンションは、<span class="filepath">Transformation.cfg</span> ファイルまたは変換データセットインクルードファイルで定義し、このファイルの Dimension パラメーターで指定する必要があります。変換設定ファイルについて詳しくは、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ディメンション </td> 
   <td colname="col2"><span class="wintitle">キー</span>列のデータ行に対応する要素を含むディメンションの名前（変換設定ファイルで定義）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指標 </td> 
   <td colname="col2"> Dimension パラメーターで指定されたディメンションに対して評価される指標の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> （オプション）レイヤー内のポイントのサイズ設定に使用する値です。デフォルト値は 100 です。値が大きいとポイントが大きくなり、値が小さいとポイントが小さくなります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> （オプション）RGB カラーベクトルで、(red,green,blue) として表されます。ベクトル内のカラーごとに、0.0 ～ 1.0 の値を入力できます。例えば、(1.0, 0.0, 0.0) は明るい赤で、(0.5, 0.5, 0.5) はグレーです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendering Mode </td> 
   <td colname="col2"> <p>（オプション）レイヤーに使用するレンダリングモードを表す整数値です。次の 3 つのモードを使用できます。 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">レンダリングモード 1。ポイントのサイズは画面空間内で定義されます（ポイントは、コンピューター画面に相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。これがデフォルトのレンダリングモードです。 </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">レンダリングモード 2。ポイントのサイズは世界空間内で定義されます（ポイントは、グローブに相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。 </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">レンダリングモード 3。ポイントのサイズは、画面空間内で定義されます。ポイントは、OpenGL のスムーズポイントを使用して描画されます。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Zip Points.layer] ファイルは以下のようにフォーマットされています。

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
