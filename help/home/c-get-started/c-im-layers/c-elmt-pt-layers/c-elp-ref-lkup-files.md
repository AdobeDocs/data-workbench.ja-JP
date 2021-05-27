---
description: 参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。
title: 参照ファイルを参照する要素ポイントレイヤーの定義
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 72%

---

# 参照ファイルを参照する要素ポイントレイヤーの定義{#define-element-point-layers-referencing-lookup-files}

参照ファイルを参照して緯度と経度のデータを取得する要素ポイントレイヤーを作成すると、各要素および関連付けられた緯度と経度を参照ファイルから取得することによって、ポイントの位置を取得できます。

>[!NOTE]
>
>ルックアップファイルを使用する代わりに、動的ポイント機能を使用して、ディメンションの各要素の名前に場所の緯度と経度を埋め込むことができます。 [動的ポイントを使用した要素ポイントレイヤーの定義](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512)を参照してください。

参照ファイルを参照する要素ポイントレイヤーを定義するには、以下のものを作成するか、既に利用可能でなければなりません。

* **また** はファイルで定 [!DNL Transformation.cfg file] 義され [!DNL transformation dataset include] たディメンション。変換設定ファイルについては、『*データセット設定ガイド*』を参照してください。

* 各データポイントのプロットに使用するデータを含む&#x200B;**参照ファイル**。このファイルには、データポイントごとにキー、経度、緯度の少なくとも 3 つのデータ列を含める必要があります。参照ファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)」を参照してください。

* 参照ファイルの場所を指定し、参照ファイル内のキー、経度、緯度の列名だけでなく、関連ディメンションおよび指標を指定する&#x200B;**レイヤーファイル**。レイヤーファイルに必要な形式について詳しくは、「[要素ポイントレイヤーファイルの形式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)」を参照してください。

   >[!NOTE]
   >
   >[!DNL Zip Points.layer]ファイル（[!DNL Geography]プロファイルと共に提供）は、 [!DNL Zipcode.dim]ファイル、 [!DNL Sessions.metric]ファイル、 [!DNL Zip Points.txt]ルックアップファイル、およびルックアップファイル内のキー、経度、緯度、名前の列の名前を識別する要素ポイントレイヤーです。

## 要素ポイント参照ファイルの形式{#section-0bc8c652c1bd40eb84078f2af71a5c06}

要素ポイントレイヤー参照ファイルには、以下の少なくとも 3 つの列を含める必要があります。

* **[!DNL Key]列：** この列には、共通キーデータを含める必要があります。これにより、Data Workbenchサーバーは、ルックアップファイル内のデータをデータセット内のデータに接続できます。[!DNL key]列は、参照ファイルの最初の列である必要があります。 この列の各行は、ディメンションの要素です。

* **[!DNL Longitude]列：** この列には、列の各データポイントの経度を含める必要があ [!DNL Key] ります。

* **[!DNL Latitude]列：** この列には、列の各データポイントの緯度を含める必要があ [!DNL Key] ります。

* **[!DNL Name]列（オプション）:** 各データポイントに対してマップに表示する名前を指定する場合は、参照ファイルに列を含めることがで [!DNL Name] きます。

[!DNL Zip Points.txt] 参照ファイルの各行は、先頭列に郵便番号が含まれ、経度、緯度、関連付けられた都市名と続きます。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## 要素ポイントレイヤーファイル形式{#section-52d7e92be8354d979af9e7a2210b76f2}

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>共通キーデータを含むルックアップファイル内の列の名前。Data Workbenchサーバーは、ルックアップファイル内のデータをデータセットに統合できます。 この列は、参照ファイル内の先頭列でなければなりません。 </p> <p>この列の各行は、ディメンションの要素です。このディメンションは、<span class="filepath">Transformation.cfg</span> ファイルまたは<span class="wintitle">変換データセットインクルード</span>ファイルで定義し、このファイルの Dimension パラメーターで指定する必要があります。変換設定ファイルについて詳しくは、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">レンダリングモード 1。ポイントのサイズは画面空間内で定義されます（ポイントは、コンピューター画面に相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。これがデフォルトのレンダリングモードです。 </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">レンダリングモード 2。ポイントのサイズは世界空間内で定義されます（ポイントは、グローブに相対的に一定のサイズに保たれます）。ポイントはポリゴンを使用して描画されるため、ポイントのサイズに上限はありません。 </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">レンダリングモード 3。ポイントのサイズは、画面空間内で定義されます。ポイントは、OpenGL のスムーズポイントを使用して描画されます。 </li> 
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
