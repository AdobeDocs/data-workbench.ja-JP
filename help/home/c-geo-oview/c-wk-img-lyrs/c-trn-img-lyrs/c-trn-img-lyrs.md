---
description: data workbenchでは、地形画像レイヤーに地球の地形画像が表示されます。
title: 地形画像レイヤーの操作
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 67%

---

# 地形画像レイヤーの操作{#working-with-terrain-image-layers}

data workbenchでは、地形画像レイヤーに地球の地形画像が表示されます。

地形画像レイヤーは、カスタム形式で[!DNL Geography]プロファイルに保存されます。 これらの画像レイヤーは、Adobeによって生成できます。または、Data Workbenchサーバーで、ユーザーが提供した地形画像を、グローブビジュアライゼーションでの使用に適した地形レイヤーに変換できます。

>[!NOTE]
>
>地形画像レイヤーを操作するには、Adobeが提供する[!DNL Terrain Images.cfg]ファイルをインストールする必要があります。 インストール手順については、「[Data WorkbenchGeography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)のインストール」を参照してください。

地形画像レイヤーを定義するには、次のファイルが必要です。

* グローブに表示する画像を含む **1 つまたは複数の地形画像ファイル**。
* **レイヤーに使用する地形画像ファイルを指定する Terrain Images.cfg** ファイル。[!DNL Terrain Images.cfg] ファイルにより、1 つ以上のソースを追加して、地形画像レイヤーを作成できます。地形画像ファイルの形式により、追加する必要のあるソースの種類が決まります。次の表に、サポートされている地形画像のファイル形式を含め、利用できる地形画像レイヤーのソースに関する説明を記載します。

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Raw unprojected bitmap </td> 
   <td colname="col2"> <p>緯度-経度で並べた（投影されていない）24 ビットのヘッダーなしの RGB ファイルから地形画像レイヤーを作成します。このファイルでは画像の上が北で、右が東です。 </p> <p>サポートされている画像形式：RAW </p> <p> <p>注意：このソースには投影情報が必要です。投影形式について詳しくは、<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">地形画像の投影情報の指定</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> General image, unprojected </td> 
   <td colname="col2"> <p>緯度-経度で並べた（投影されていない）24 ビットの画像形式から地形画像レイヤーを作成します。このファイルでは画像の上が北で、右が東です。 </p> <p>サポートされている画像形式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：このソースには投影情報が必要です。投影形式について詳しくは、<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">地形画像の投影情報の指定</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Image with embedded projection </td> 
   <td colname="col2"> <p>画像ファイルに測地データが埋め込まれている画像形式から、地形画像レイヤーを作成します。投影情報は画像から抽出されます。 </p> <p>サポートされている画像形式：Erdas（IMG）、GeoTIFF </p> <p> <p>注意：通常このソースでは投影情報を必要としませんが、必要であれば、こうした情報の追加もサポートされています。投影形式について詳しくは、<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">地形画像の投影情報の指定</a>を参照してください。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**地形画像レイヤー**&#x200B;を定義するには

1. Data Workbenchの[!DNL Admin] / [!DNL Dataset and Profile]タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして[!DNL Servers Manager]ワークスペースを開きます。

1. [!DNL Servers Manager]ウィンドウ内で、目的のData Workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。

1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。

1. [!DNL Terrain Images.cfg]のサーバー名列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg.]の[!DNL Temp]列にチェックマークが表示されます

1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL from the workbench]**&#x200B;をクリックします。 [!DNL Terrain Images.cfg]ウィンドウが表示されます。

1. [!DNL Terrain Images]ウィンドウで、「**[!UICONTROL component]**」をクリックして内容を表示します。

1. **[!UICONTROL Sources]** > **[!UICONTROL Add new]**&#x200B;を右クリックし、次のソースタイプのいずれかを選択します。

   * **[!UICONTROL Raw unprojected bitmap]**&#x200B;に移動します。（このソースタイプは、一旦追加されると、[!DNL Terrain Images] ウィンドウで RawTerrainSource というラベルが付きます。）

   * **[!UICONTROL General image, unprojected]**&#x200B;に移動します。（このソースタイプは、一旦追加されると、[!DNL Terrain Images] ウィンドウで GDALTerrainSource というラベルが付きます。）

   * **[!UICONTROL Image with embedded projection]**&#x200B;に移動します。（このソースタイプは、一旦追加されると、[!DNL Terrain Images] ウィンドウで GDALTerrainSource というラベルが付きます。）

1. 必要に応じて、次のサンプルファイルとパラメーター表をガイドとして使用し、ソースのパラメーターを編集します。

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> すべてのソースに対してオプションです。ソース画像に適用されるガンマ補正を指定します。data workbench は通常、高いガンマ設定で動作するため、このパラメーターの設定が望ましい場合があります。デフォルト値は 1 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Height </td> 
   <td colname="col2"> Raw unprojected bitmap 画像に対して必須です。ソース画像の高さをピクセルで指定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Projection Info </td> 
   <td colname="col2"> <p>Raw unprojected bitmap 画像と General image, unprojected 画像に対して必須ですが、Image with embedded projection 画像に対してもサポートされています。Data Workbench<span class="wintitle"> Geography</span>では、地形画像レイヤーに対して緯度 — 経度投影法と横メルカトル(TM)投影法をサポートしています。 デフォルトの投影形式は、緯度-経度図法（LatLonProjection）です。 </p> <p>投影形式について詳しくは、「 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 地形画像の投影情報の指定</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Source Image </td> 
   <td colname="col2">すべてのソースに対して必須です。ソース画像ファイルの名前を指定します。ファイル名またはワイルドカードパターンを使用できます。パターンの使用は、例えば、異なる日付で同じ地域の画像がアップロードされ、関連するメタデータが変更されない場合に役に立ちます。したがって、「<span class="filepath"> Tysons Corner *.raw</span>」のようなパターンは、新しい画像が追加される際に<span class="filepath"> Tysons Corner 050211.raw</span>、<span class="filepath"> Tysons Corner 050218.raw</span>などからレイヤーを作成します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tile Compression Quality </td> 
   <td colname="col2"> <p>すべてのソースに対してオプションです。JPEG 圧縮用に、0 ～ 100 の整数で画像サイズと画質のバランスを指定します。（デフォルト値は 0 です。）数値が高いほど画質が良くなりますが、大きな画像が生成され、data workbench ユーザーのダウンロード時間が長くなります。 </p> <p>70未満で画像を圧縮すると、画像の劣化が生じる場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tile Compressor </td> 
   <td colname="col2"> すべてのソースに対してオプションです。出力ファイルの作成に使用する圧縮方式を指定します。現在サポートされている方式は、RAWRGB（デフォルト、圧縮なし）と JPEG だけです。プロファイルの同期中に送信されるレイヤーのサイズを低減するには、JPEG 圧縮を使用します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Width </td> 
   <td colname="col2"> Raw unprojected bitmap 画像に対して必須です。ソース画像の幅をピクセルで指定します。 </td> 
  </tr> 
 </tbody> 
</table>

1. 次の表をガイドとして使用し、Source Image Location」、「Temp Image Storage」および「Write Layers To」パラメーターを編集します。これらのパラメーターは、このファイルの Sources セクションで定義するすべての地形画像ソースに適用されます。

   | パラメーター | 説明 |
   |---|---|
   | Source Image Location | 必須。地形レイヤーに変換する画像をスキャンするディレクトリ。絶対パスでない場合、data workbench サーバーのインストールディレクトリに対する相対パスと解釈されます。 |
   | Temp Image Storage | （オプション）ソース画像を地形レイヤーに変換する際に使用する一時ファイルの記憶に使用するディレクトリの名前。絶対パスでない場合、data workbench サーバーのインストールディレクトリに対する相対パスと解釈されます。デフォルトの場所は Temp ディレクトリです。 |
   | Write Layers To | 必須。地形レイヤーの出力先ディレクトリ。 通常、これはプロファイルディレクトリのMapsサブディレクトリで、 [!DNL Globe]ビジュアライゼーションでレイヤーを検索できます。 |

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックして、ファイルを保存します。

1. 更新したファイルをData Workbenchサーバーマシンの[!DNL Server Files Manager]に保存するには、[!DNL Temp]列の[!DNL Terrain Images.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;をクリックします。
