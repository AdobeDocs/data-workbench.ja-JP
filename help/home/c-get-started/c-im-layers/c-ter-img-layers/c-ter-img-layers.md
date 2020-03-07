---
description: 地形画像レイヤーには、地球の地形画像が表示されます。
solution: Analytics
title: 地形画像レイヤー
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 地形画像レイヤー{#terrain-image-layers}

地形画像レイヤーには、地球の地形画像が表示されます。

[!DNL Terrain image layers] は、カスタム形式でプロ [!DNL Geography] ファイルに保存されます。 これらの画像レイヤーはアドビが生成できます。また、Data Workbenchサーバーでは、ユーザーが提供した地形画像を、グローブビジュアライゼーションでの使用に適した地形レイヤーに変換できます。

>[!NOTE]
>
>を使用するには、ア [!DNL terrain image layers]ドビが提供するファイルをイ [!DNL Terrain Images.cfg] ンストールする必要があります。

地形画像レイヤーを定義するには、次のファイルが必要です。

* グローブに表示する画像を含む **1 つまたは複数の地形画像ファイル**。
* **レイヤーに使用する地形画像ファイルを指定する[!DNL Terrain Images.cfg]ファイル**。The [!DNL Terrain Images.cfg] file enables you to add one or more sources to create a [!DNL terrain image layer]. 地形画像ファイルの形式により、追加する必要のあるソースの種類が決まります。次の表に、サポートされている地形画像のファイル形式を含め、利用できる地形画像レイヤーのソースに関する説明を記載します。

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> タイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Raw unprojected bitmap </p> </td> 
   <td colname="col2"> <p>緯度-経度で並べた（投影されていない）24 ビットのヘッダーなしの RGB ファイルから<span class="wintitle">地形画像レイヤー</span>を作成します。このファイルでは画像の上が北で、右が東です。 </p> <p>サポートされている画像形式：RAW </p> <p> <p>注意：このソースには投影情報が必要です。投影形式について詳しくは、地形画像の投影 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 情報の指定を参照してください</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>General image, unprojected </p> </td> 
   <td colname="col2"> <p>緯度-経度で並べた（投影されていない）24 ビットの画像形式から<span class="wintitle">地形画像レイヤー</span>を作成します。このファイルでは画像の上が北で、右が東です。 </p> <p>サポートされている画像形式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：このソースには投影情報が必要です。投影形式について詳しくは、地形画像の投影 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 情報の指定を参照してください</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Image with embedded projection </p> </td> 
   <td colname="col2"> <p>画像ファイルに測地データが埋め込まれている画像形式から、<span class="wintitle">地形画像レイヤー</span>を作成します。投影情報は画像から抽出されます。 </p> <p>サポートされている画像形式：Erdas（IMG）、GeoTIFF </p> <p> <p>注意：通常このソースでは投影情報を必要としませんが、必要であれば、こうした情報の追加もサポートされています。投影形式について詳しくは、地形画像の投影 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 情報の指定を参照してください</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**地形画像レイヤー**&#x200B;を定義するには

1. Data Workbenchの「/」タブで、サムネ **[!UICONTROL Admin]** ールをク **[!UICONTROL Dataset and Profile]** リックしてワ **[!UICONTROL Servers Manager]** ークスペースを開 [!DNL Servers Manager] きます。
1. Within the [!DNL Servers Manager] window, right-click the icon of the desired Data Workbench server and click **[!UICONTROL Server Files]**.
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Terrain Images.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg].
1. Right-click the newly created check mark in the **[!UICONTROL Temp]** column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Terrain Images.cfg] window appears.
1. In the [!DNL Terrain Images] window, click **[!UICONTROL component]** to view its contents.
1. Right-click **[!UICONTROL Sources]** > **[!UICONTROL Add new]** and choose one of the following source types:

   * **[!UICONTROL Raw unprojected bitmap]**&#x200B;をインストールします。（このソースタイプは、一旦追加されると、[!DNL Terrain Images] ウィンドウで RawTerrainSource というラベルが付きます。）

   * **[!UICONTROL General image, unprojected]**&#x200B;をインストールします。(Once added, this source type is labeled [!DNL GDALTerrainSource] in the [!DNL Terrain Images] window.)

   * **[!UICONTROL Image with embedded projection]**&#x200B;をインストールします。(Once added, this source type is labeled [!DNL GDALTerrainSource] in the [!DNL Terrain Images] window.)

1. 必要に応じて、次のサンプルファイルとパラメーター表をガイドとして使用し、ソースのパラメーターを編集します。

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>すべてのソースに対してオプションです。ソース画像に適用されるガンマ補正を指定します。Data Workbenchは通常、高いガンマ設定で実行されるので、この設定が望ましい場合があります。 デフォルト値は 1 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Height </p> </td> 
   <td colname="col2"> <p>Raw unprojected bitmap 画像に対して必須です。ソース画像の高さをピクセルで指定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Projection Info </p> </td> 
   <td colname="col2"> <p>Raw unprojected bitmap 画像と General image, unprojected 画像に対して必須ですが、Image with embedded projection 画像に対してもサポートされています。Data Workbenchでは、地形画像レイヤーの緯度 — 経度投影法と横メルカトル(TM)投影法をサポートしています。 デフォルトの投影形式は、緯度-経度図法（LatLonProjection）です。 </p> <p>投影形式について詳しくは、「 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 地形画像の投影情報の指定</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Source Image </p> </td> 
   <td colname="col2"> <p>すべてのソースに対して必須です。ソース画像ファイルの名前を指定します。ファイル名またはワイルドカードパターンを使用できます。パターンの使用は、例えば、異なる日付で同じ地域の画像がアップロードされ、関連するメタデータが変更されない場合に役に立ちます。そのため、<span class="filepath">Tysons Corner *.raw</span> のようなパターンは、新しい画像が追加されるにつれ、<span class="filepath">Tysons Corner 050211.raw</span>、<span class="filepath">Tysons Corner 050218.raw</span> などからレイヤーを作成します。ファイルのパラメーターがそれ以外同一であれば、追加の設定は不要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tile Compression Quality </p> </td> 
   <td colname="col2"> <p>すべてのソースに対してオプションです。JPEG 圧縮用に、0 ～ 100 の整数で画像サイズと画質のバランスを指定します。（デフォルト値は 0 です。）数値が高いほど画質は向上しますが、Data Workbenchユーザーの場合は画像が大きくなり、ダウンロード時間が長くなります。 </p> <p> <p>注意：70 未満で画像を圧縮すると、画質劣化を生じる場合があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tile Compressor </p> </td> 
   <td colname="col2"> <p>すべてのソースに対してオプションです。出力ファイルの作成に使用する圧縮方式を指定します。現在サポートされている方式は、RAWRGB（デフォルト、圧縮なし）と JPEG だけです。プロファイルの同期中に送信されるレイヤーのサイズを低減するには、JPEG 圧縮を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Width </p> </td> 
   <td colname="col2"> <p>Raw unprojected bitmap 画像に対して必須です。ソース画像の幅をピクセルで指定します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 次の表をガイドとして使用し、Source Image Location」、「Temp Image Storage」および「Write Layers To」パラメーターを編集します。これらのパラメーターは、このファイルの [!DNL Sources] セクションで定義するすべての地形画像ソースに適用されます。

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Source Image Location </p> </td> 
   <td colname="col2"> <p>必須。地形レイヤーに変換する画像をスキャンするディレクトリ。絶対パスでない場合、Data Workbenchサーバーのインストールディレクトリを基準とした相対パスと解釈されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Temp Image Storage </p> </td> 
   <td colname="col2"> <p>(オプション)ソース画像を地形レイヤーに変換する際に使用する一時ファイルの記憶に使用するディレクトリの名前。絶対パスでない場合、Data Workbenchサーバーのインストールディレクトリを基準とした相対パスと解釈されます。 デフォルトの場所は <span class="wintitle">Temp</span> ディレクトリです。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Write Layers To </p> </td> 
   <td colname="col2"> <p>必須。地形レイヤーの出力先ディレクトリ。通常はプロファイルディレクトリの Maps サブディレクトリです。Maps サブディレクトリに設定すると、グローブビジュアライゼーションでレイヤーを検索できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.
1. To save an updated file to the Data Workbench server computer, in the [!DNL Server Files Manager], right-click the check mark for [!DNL Terrain Images.cfg] in the [!DNL Temp] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

