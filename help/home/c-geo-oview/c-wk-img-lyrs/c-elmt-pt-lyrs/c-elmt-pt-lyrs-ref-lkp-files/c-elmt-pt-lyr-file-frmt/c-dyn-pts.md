---
description: 動的ポイントを使用して要素ポイントレイヤーを作成すると、ディメンションの各要素に緯度と経度のデータが埋め込まれます。
title: 動的ポイントを使用した要素ポイントレイヤーの定義
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 95%

---

# 動的ポイントを使用した要素ポイントレイヤーの定義{#defining-element-point-layers-using-dynamic-points}

動的ポイントを使用して要素ポイントレイヤーを作成すると、ディメンションの各要素に緯度と経度のデータが埋め込まれます。

動的ポイントを使用して要素ポイントレイヤーを定義するには、以下のものを作成するか、既に利用可能でなければなりません。

* ****[!DNL Transformation.cfg] ファイルまたは 変換データセットインクルードファイルで定義され、各要素に「latitude,longitude」または「latitude,longitude,name」という文字列が含まれているディメンション。

   ディメンションを作成する手順については、『*データセット設定ガイド*』を参照してください。

* **関連ディメンションを指定するレイヤーファイル。**

   レイヤーファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981)」を参照してください。

>[!NOTE]
>
>[!DNL Dynamic Points]を使用する場合、レイヤーファイルで指定したディメンションのカーディナリティが妥当であることを確認する必要があります。 データセットの行ごとに緯度と経度が異なる場合、ディメンションはすぐにいっぱいになり、大部分の行は小さい要素に分類されます。小さい要素は緯度と経度を持たないので、グローブ上に表示されません。

## 要素ポイントレイヤーファイルの形式  {#section-bbcc2baa2f754dba81eba93339a97cbd}

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

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ディメンション </td> 
   <td colname="col2"> <p>ディメンションの名前（変換設定ファイルで定義）。以下の例に示すように、「latitude,longitude」または「latitude,longitude,name」という文字列を持つ要素を含める必要があります。 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 指標 </td> 
   <td colname="col2"> Dimension パラメーターで指定されたディメンションに対して評価される指標の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dynamic Points </td> 
   <td colname="col2"> 動的ポイントを有効にします。true に設定します。 </td> 
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
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">レンダリングモード 1。ポイントのサイズは画面空間内で定義されます（ポイントは、コンピューター画面に相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。これがデフォルトのレンダリングモードです。 </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">レンダリングモード 2。ポイントのサイズは世界空間内で定義されます（ポイントは、グローブに相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。 </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">レンダリングモード 3。ポイントのサイズは、画面空間内で定義されます。ポイントは、OpenGL のスムーズポイントを使用して描画されます。 </li> 
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
