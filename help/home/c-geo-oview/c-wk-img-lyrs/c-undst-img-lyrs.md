---
description: Geographyプロファイルレイヤー、画像レイヤーのタイプ、新しいレイヤーの作成に関する概念情報です。
solution: Analytics
title: 画像レイヤーについて
topic: Data workbench
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 画像レイヤーについて{#understanding-imagery-layers}

Geographyプロファイルレイヤー、画像レイヤーのタイプ、新しいレイヤーの作成に関する概念情報です。

## 画像レイヤーのタイプ {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbenchでは、Data Workbench [!DNL Geography] で次のタイプの画像レイヤーを表示できます。

* **地形画像レイヤー：** このタイプのレイヤーには、地球の地形画像が表示され、その上に地理データを表示できます。 data workbenchのグローブビジュアライゼーションは、地形画像レイヤーの例です。 See [Working with Terrain Image Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

* **要素ポイントレイヤー：** このタイプのレイヤーでは、ディメンションの各要素に対してグローブ上の1点が表示されます。 See [Working with Element Point Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9).

* **ベクトルレイヤー：** このタイプのレイヤーでは、ベクトルデータ（ラインアート）がグローブ上に表示されます。 See [Working with Vector Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

data workbench では、特定の分析タスクに対して、これらのレイヤーのうちどのレイヤーを表示するかを選択できます。

## Geography プロファイルレイヤー {#section-4d9fb9b357764493a4d97d2b4068bb67}

[!DNL Geography] プロファイルでは、デフォルトの画像レイヤーのセットが提供されます。これらは data workbench サーバーのインストールディレクトリ内の Profiles\Geography\Maps フォルダーに保存されています。

* **青大理石2km:** この地形画像レイヤーは、世界の3Dマップを作成します。このマップは、グローブビジュアライゼーションをワークスペースに追加すると表示されます。 このレイヤーが選択されていない場合、グローブは表示されませんが、他のレイヤーは表示されます。ファイル [!DNL Blue Marble 2km.layer] はファイルを参照 [!DNL Blue Marble 2km.tsi] します。

   グローブビジュアライゼーションの操作について詳しくは、『 *Data Workbenchユーザーガイド』を参照してください*。

* **郵便番号：** この要素ポイントレイヤーを使用すると、米国の郵便番号を使用して、データセット内の場所をマッピングできます。 [!DNL Zip Points.txt] ルックアップファイル（Adobe が提供）には、米国のすべての郵便番号と各郵便番号の緯度と経度のリストが含まれています。The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. データセット内で定義する郵便番号のディメンション（[!DNL Zipcode.dim]）の各要素は、[!DNL Zip Points.txt] ルックアップファイルに記載されている、その郵便番号の緯度と経度を使用してグローブ上にマッピングされます。

   For information about defining dimensions, see the *Dataset Configuration Guide.*

* **境界：** このベクトルレイヤーは、国などの主要な世界の政治的境界と、湖や島などの地球の自然な物理的特徴の境界を提供します。 ファイ [!DNL Boundaries.layer] ル参照，,,,,, [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec]1つ以上のファ [!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec] イル参照。

* **IP座標：** この要素ポイントレイヤーは、動的ポイントを使用して、IPアドレスを使用してデータセット内の場所をマッピングできます。 [!DNL IP Coordinates.layer] ファイルでは、座標のディメンション（[!DNL Coordinates.dim]）を参照します。また、各座標のグローブ上のポイントのサイズを決定する際に使用する指標として、Visitors 指標を指定します。

[!DNL Geography] プロファイルや、ご使用のインストール内の他のプロファイルには、ほかにも Adobe が提供した画像レイヤーやお客様の会社が作成した画像レイヤーが含まれている場合があります。

## 新しいレイヤーの作成 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. 新しいレイヤーはすべて、以下の要件を満たす必要があります。

* The [!DNL .layer] file must adhere to the format of one of the supported layer types.
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary.
* The referenced lookup file also must be stored within the data workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

各タイプのレイヤーファイルとその関連ファイルの形式およびパラメーターについて詳しくは、この章の該当するレイヤータイプの節を参照してください。
