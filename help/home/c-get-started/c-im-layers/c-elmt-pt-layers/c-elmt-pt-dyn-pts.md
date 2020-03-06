---
description: 動的ポイントを使用して要素ポイントレイヤーを作成すると、ディメンションの各要素に緯度と経度のデータが埋め込まれます。
solution: Analytics
title: 動的ポイントを使用して要素ポイントレイヤーを定義する
topic: Data workbench
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Define element point layers using dynamic points{#define-element-point-layers-using-dynamic-points}

動的ポイントを使用して要素ポイントレイヤーを作成すると、ディメンションの各要素に緯度と経度のデータが埋め込まれます。

動的ポイントを使用して要素ポイントレイヤーを定義するには、以下のものを作成するか、既に利用可能でなければなりません。

* A dimension, defined in the [!DNL Transformation.cfg] file or a [!DNL transformation dataset include] file, in which each element contains the string “latitude,longitude” or “latitude,longitude,name.”

   ディメンションを作成する手順については、『*データセット設定ガイド*』を参照してください。

* 関連ディメンションを指定するレイヤーファイル。

レイヤーファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0)」を参照してください。

>[!NOTE]
>
>When using [!DNL Dynamic Points], it is essential to ensure that the cardinality of the dimension specified in the layer file is reasonable. データセットの行ごとに緯度と経度が異なる場合、ディメンションはすぐにいっぱいになり、大部分の行は小さい要素に分類されます。小さい要素は緯度と経度を持たないので、グローブ上に表示されません。

## Element point layer file format {#section-0645fbc761c14bb986f3d6f02df407a0}

動的ポイントを使用する各要素ポイントレイヤーファイルは、以下のテンプレートを使用してフォーマットする必要があります。

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>ディメンションの名前（変換設定ファイルで定義）。以下の例に示すように、「latitude,longitude」または「latitude,longitude,name」という文字列を持つ要素を含める必要があります。 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metric </td> 
   <td colname="col2"> Dimension パラメーターで指定されたディメンションに対して評価される指標の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Points </td> 
   <td colname="col2"> 動的ポイントを有効にします。true に設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> (オプション)レイヤー内のポイントのサイズ設定に使用する値です。デフォルト値は 100 です。値が大きいとポイントが大きくなり、値が小さいとポイントが小さくなります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> (オプション)RGB カラーベクトルで、(red,green,blue) として表されます。ベクトル内のカラーごとに、0.0 ～ 1.0 の値を入力できます。例えば、(1.0, 0.0, 0.0) は明るい赤で、(0.5, 0.5, 0.5) はグレーです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendering Mode </td> 
   <td colname="col2"> <p>(オプション)レイヤーに使用するレンダリングモードを表す整数値です。次の 3 つのモードを使用できます。 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">レンダリングモード 1。ポイントのサイズは画面空間内で定義されます（ポイントは、コンピューター画面に相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。これがデフォルトのレンダリングモードです。 </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">レンダリングモード 2。ポイントのサイズは世界空間内で定義されます（ポイントは、グローブに相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。 </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">レンダリングモード 3。ポイントのサイズは、画面空間内で定義されます。ポイントは、OpenGL のスムーズポイントを使用して描画されます。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL IP Coordinates.layer] ファイルは以下のようにフォーマットされています。

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

