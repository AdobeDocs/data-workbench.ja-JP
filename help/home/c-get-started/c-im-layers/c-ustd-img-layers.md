---
description: 画像レイヤーに関する概念情報です。
solution: Analytics
title: 画像レイヤーについて
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 画像レイヤーについて{#about-imagery-layers}

画像レイヤーに関する概念情報です。

## Types of imagery layers {#section-891cbf61e8334690bd203a2bb9761b25}

Data Workbenchでは、次のタイプの画像レイヤーを表示できます。

* **[!UICONTROL Terrain image layer]:**このタイプのレイヤーには、地球の地形画像が表示され、その上に地理データを表示できます。 グローブビジュアライゼーションは、地形画像レイヤーの例です。詳しくは、「[地形画像レイヤーの操作](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)」を参照してください。

* **[!UICONTROL Element point layer]:**このタイプのレイヤーでは、ディメンションの各要素に対してグローブ上の1点が表示されます。 See[Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:**このタイプのレイヤーでは、ベクトルデータ（ラインアート）がグローブ上に表示されます。 See[Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]**&#x200B;プレゼンテーションオーバーレイを使用して、ビジュアライゼーションへの注釈の付与やビジュアライゼーションの明確化を行うことができます。テキストコールアウト、矢印、画像および色分けの追加によってデータを強調および明確化したうえで、他のユーザーと共有できます。

Data Workbenchでは、特定の分析タスクに対して表示するレイヤーを選択できます。

## Geography profile layers {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

The [!DNL Geography] profile provides you with a set of default imagery layers, which are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:**この地形画像レイヤーは、世界の3Dマップを作成します。このマップは、グローブビジュアライゼーションをワークスペースに追加すると表示されます。 このレイヤーが選択されていない場合、グローブは表示されませんが、他のレイヤーは表示されます。ファイル[!DNL Blue Marble 2km.layer]はファイルを参照[!DNL Blue Marble 2km.tsi]します。

* **[!UICONTROL Zip Points]:**この要素ポイントレイヤーを使用すると、米国の郵便番号を使用して、データセット内の場所をマッピングできます。[!DNL Zip Points.txt]ルックアップファイル（Adobe が提供）には、米国のすべての郵便番号と各郵便番号の緯度と経度のリストが含まれています。The[!DNL Zip Points.layer]file references the[!DNL Zip Points.txt]file and the[!DNL Zipcode.dim]file and contains the configuration parameters needed to display the locations on the globe. データセット内で定義する郵便番号のディメンション（[!DNL Zipcode.dim]）の各要素は、[!DNL Zip Points.txt]ルックアップファイルに記載されている、その郵便番号の緯度と経度を使用してグローブ上にマッピングされます。

   ディメンションの定義について詳しくは、『*データセット設定ガイド*』を参照してください。

* **[!UICONTROL Boundaries]:**このベクトルレイヤーは、国などの主要な世界の政治的境界と、湖や島などの地球の自然な物理的特徴の境界を提供します。 ファイ[!DNL Boundaries.layer]ル参照，,,,,,[!DNL mwcoast.vec],[!DNL mwisland.vec],[!DNL mwlake.vec],[!DNL mwnation.vec],[!DNL mwriver.vec]1つ以上のファ[!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec]イル参照。

* **[!UICONTROL IP Coordinates]:**この要素ポイントレイヤーは、動的ポイントを使用して、IPアドレスを使用してデータセット内の場所をマッピングできます。[!DNL IP Coordinates.layer]ファイルでは、座標のディメンション（[!DNL Coordinates.dim]）を参照します。また、各座標のグローブ上のポイントのサイズを決定する際に使用する指標として、Visitors 指標を指定します。

[!UICONTROLNL Geography] プロファイルや、ご使用のインストール内の他のプロファイルには、ほかにも Adobe が提供した画像レイヤーやお客様の会社が作成した画像レイヤーが含まれている場合があります。

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. 新しいレイヤーはすべて、以下の要件を満たす必要があります。

* The [!DNL .layer] file must adhere to the format of one of the supported layer types.
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary.
* The referenced lookup file also must be stored within the Data Workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

各タイプのレイヤーファイルとその関連ファイルの形式およびパラメーターについて詳しくは、この章の該当するレイヤータイプの節を参照してください。
