---
description: 概念Geographyプロファイルレイヤー、画像レイヤーのタイプ、新しいレイヤーの作成に関する情報。
title: 画像レイヤーについて
uuid: 8f4618bf-d8bd-4d21-a29e-ab2871d781ca
exl-id: ffe084ec-db8b-46f4-8266-0f1b771b3349
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 37%

---

# 画像レイヤーについて{#understanding-imagery-layers}

概念Geographyプロファイルレイヤー、画像レイヤーのタイプ、新しいレイヤーの作成に関する情報。

## 画像レイヤーのタイプ {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data Workbenchの[!DNL Geography]では、Data Workbenchで次のタイプの画像レイヤーを表示できます。

* **地形画像レイヤー：** このタイプのレイヤーでは、地球の地形画像を表示し、その上に地理データを表示できます。data workbenchのグローブビジュアライゼーションは、地形画像レイヤーの例です。 [地形画像レイヤーの操作](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)を参照してください。

* **要素ポイントレイヤー：** このタイプのレイヤーでは、ディメンションの各要素に対してグローブ上の1つのポイントを表示します。[要素ポイントレイヤーの操作](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9)を参照してください。

* **ベクトルレイヤー：** このタイプのレイヤーでは、グローブ上にベクトルデータ（ラインアート）が表示されます。[ベクトルレイヤーの操作](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620)を参照してください。

data workbench では、特定の分析タスクに対して、これらのレイヤーのうちどのレイヤーを表示するかを選択できます。

## Geography プロファイルレイヤー {#section-4d9fb9b357764493a4d97d2b4068bb67}

[!DNL Geography] プロファイルでは、デフォルトの画像レイヤーのセットが提供されます。これらは data workbench サーバーのインストールディレクトリ内の Profiles\Geography\Maps フォルダーに保存されています。

* **Blue Marble 2km:** この地形画像レイヤーは、ワークスペースにグローブビジュアライゼーションを追加したときに表示される、世界の3Dマップを作成します。このレイヤーが選択されていない場合、グローブは表示されませんが、他のレイヤーは表示されます。[!DNL Blue Marble 2km.layer]ファイルは[!DNL Blue Marble 2km.tsi]ファイルを参照します。

   グローブビジュアライゼーションの操作について詳しくは、『Data Workbenchユーザーガイド&#x200B;*』を参照してください。*

* **郵便番号：** この要素ポイントレイヤーを使用すると、米国の郵便番号を使用してデータセット内の場所をマッピングできます。[!DNL Zip Points.txt] ルックアップファイル（Adobe が提供）には、米国のすべての郵便番号と各郵便番号の緯度と経度のリストが含まれています。[!DNL Zip Points.layer]ファイルは、[!DNL Zip Points.txt]ファイルと[!DNL Zipcode.dim]ファイルを参照し、グローブ上の場所を表示するのに必要な設定パラメーターを含みます。 データセット内で定義する郵便番号のディメンション（[!DNL Zipcode.dim]）の各要素は、[!DNL Zip Points.txt] ルックアップファイルに記載されている、その郵便番号の緯度と経度を使用してグローブ上にマッピングされます。

   ディメンションの定義について詳しくは、『*データセット設定ガイド』を参照してください。*

* **境界：** このベクトルレイヤーは、国などの主要な世界の政治的境界と、湖や島などの地球の自然な物理的特徴の境界を提供します。[!DNL Boundaries.layer]ファイルは、[!DNL mwcoast.vec]、[!DNL mwisland.vec]、[!DNL mwlake.vec]、[!DNL mwnation.vec]、[!DNL mwriver.vec]、[!DNL mwstate.vec]、[!DNL US states.vec]、[!DNL world boundaries.vec]の1つ以上のファイルを参照します。

* **IP座標：** この要素ポイントレイヤーでは、動的ポイントを使用して、IPアドレスを使用してデータセット内の場所をマッピングできます。[!DNL IP Coordinates.layer] ファイルでは、座標のディメンション（[!DNL Coordinates.dim]）を参照します。また、各座標のグローブ上のポイントのサイズを決定する際に使用する指標として、Visitors 指標を指定します。

[!DNL Geography] プロファイルや、ご使用のインストール内の他のプロファイルには、ほかにも Adobe が提供した画像レイヤーやお客様の会社が作成した画像レイヤーが含まれている場合があります。

## 新しいレイヤーの作成 {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

新しい画像レイヤーを作成するには、 [!DNL Geography]プロファイルに含まれる適切なタイプのレイヤーファイルを任意のProfiles\*profile name*\Mapsフォルダーにコピーし、必要に応じてファイルの名前を変更して編集します。 新しいレイヤーはすべて、以下の要件を満たす必要があります。

* [!DNL .layer]ファイルは、サポートされているレイヤータイプのいずれかの形式に従う必要があります。
* 必要に応じて、[!DNL .layer]ファイルは、適切なルックアップファイルとディメンションファイルを参照する必要があります。
* 参照先の参照ファイルも、Data Workbenchサーバーのインストールディレクトリ内に保存する必要があります。また、そのパスは[!DNL .layer]ファイルで正確に指定する必要があります。

各タイプのレイヤーファイルとその関連ファイルの形式およびパラメーターについて詳しくは、この章の該当するレイヤータイプの節を参照してください。
