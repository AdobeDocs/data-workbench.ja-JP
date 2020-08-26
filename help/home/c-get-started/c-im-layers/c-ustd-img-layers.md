---
description: 画像レイヤーに関する概念情報です。
solution: Analytics
title: 画像レイヤーについて
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
translation-type: tm+mt
source-git-commit: f4b37f50b115a1e1d2c9d000897a8fa47b03b233
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 60%

---


# 画像レイヤーについて{#about-imagery-layers}

画像レイヤーに関する概念情報です。

## Types of imagery layers {#section-891cbf61e8334690bd203a2bb9761b25}

次のタイプの画像レイヤーをData Workbenchに表示できます。

* **[!UICONTROL 地形画像レイヤー]：**&#x200B;このタイプのレイヤーでは地球の地形画像を表示します。この上に地理データを表示できます。グローブビジュアライゼーションは、地形画像レイヤーの例です。詳しくは、「 [地形画像レイヤーの操作](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL 要素ポイントレイヤー]：**&#x200B;このタイプのレイヤーでは、ディメンションの各要素に対して 1 つのポイントをグローブに表示します。See [Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL ベクトルレイヤー]：**&#x200B;このタイプのレイヤーでは、ベクトルデータ（線画）をグローブに表示します。See [Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL プレゼンテーションレイヤー]** ：プレゼンテーションオーバーレイを使用して、ビジュアライゼーションに注釈を付け、明確にします。 テキストコールアウト、矢印、画像および色分けの追加によってデータを強調および明確化したうえで、他のユーザーと共有できます。

Data Workbenchでは、特定の分析タスクに対して表示するこれらのレイヤーを選択できます。

## Geography profile layers {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

The [!DNL Geography] profile provides you with a set of default imagery layers, which are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]：**&#x200B;この地形画像レイヤーにより世界の 3 次元マップが作成されます。これは、グローブビジュアライゼーションをワークスペースに追加すると表示されるマップです。このレイヤーが選択されていない場合、グローブは表示されませんが、他のレイヤーは表示されます。フ [!DNL Blue Marble 2km.layer] ァイルはファイルを参照し [!DNL Blue Marble 2km.tsi] ます。

* **[!UICONTROL Zip Points]：**&#x200B;この要素ポイントレイヤーにより、米国の郵便番号を使用してデータセットの場所をマッピングできます。[!DNL Zip Points.txt] ルックアップファイル（Adobe が提供）には、米国のすべての郵便番号と各郵便番号の緯度と経度のリストが含まれています。The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. データセット内で定義する郵便番号のディメンション（[!DNL Zipcode.dim]）の各要素は、[!DNL Zip Points.txt] ルックアップファイルに記載されている、その郵便番号の緯度と経度を使用してグローブ上にマッピングされます。

   ディメンションの定義について詳しくは、『*データセット設定ガイド*』を参照してください。

* **[!UICONTROL Boundaries]：**&#x200B;このベクトルレイヤーでは、世界の主要な政治的境界（国など）と、地球の自然の物理的特徴による境界（湖や島など）が提供されます。フ [!DNL Boundaries.layer] ァイルは、1つ以上の [!DNL mwcoast.vec],, [!DNL mwisland.vec][!DNL mwlake.vec][!DNL mwnation.vec][!DNL mwriver.vec][!DNL mwstate.vec][!DNL US states.vec][!DNL world boundaries.vec] ,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,

* **[!UICONTROL IP Coordinates]：**&#x200B;この要素ポイントレイヤーでは、動的ポイントを使用して、IP アドレスを使用しているデータセットの場所をマッピングできます。[!DNL IP Coordinates.layer] ファイルでは、座標のディメンション（[!DNL Coordinates.dim]）を参照します。また、各座標のグローブ上のポイントのサイズを決定する際に使用する指標として、Visitors 指標を指定します。

Your [!UICONTROL NL Geography] profile or other profiles in your installation may contain additional imagery layers that Adobe provided or your company created.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. 新しいレイヤーはすべて、以下の要件を満たす必要があります。

* The [!DNL .layer] file must adhere to the format of one of the supported layer types.
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary.
* The referenced lookup file also must be stored within the Data Workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

各タイプのレイヤーファイルとその関連ファイルの形式およびパラメーターについて詳しくは、この章の該当するレイヤータイプの節を参照してください。
