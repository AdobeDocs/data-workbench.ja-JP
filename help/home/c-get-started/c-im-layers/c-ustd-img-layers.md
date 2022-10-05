---
description: 画像レイヤーに関する概念情報です。
title: 画像レイヤーについて
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
exl-id: c6d30747-70d2-4489-ad64-fd131e76a7a2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 40%

---

# 画像レイヤーについて{#about-imagery-layers}

{{eol}}

画像レイヤーに関する概念情報です。

## 画像レイヤーのタイプ {#section-891cbf61e8334690bd203a2bb9761b25}

以下のタイプの画像レイヤーをData Workbenchで表示できます。

* **[!UICONTROL Terrain image layer]:** このタイプのレイヤーは、地球の地形画像を表示し、その上に地理データを表示できます。 グローブビジュアライゼーションは、地形画像レイヤーの例です。詳しくは、「 [地形画像レイヤーの操作](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).

* **[!UICONTROL Element point layer]:** このタイプのレイヤーでは、ディメンションの各要素に対してグローブ上の 1 点が表示されます。 詳しくは、 [要素ポイントレイヤーの操作](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd).

* **[!UICONTROL Vector layer]:** このタイプのレイヤーは、グローブ上にベクトルデータ（ラインアート）を表示します。 詳しくは、 [ベクトルレイヤーの操作](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]**&#x200B;プレゼンテーションオーバーレイを使用して、ビジュアライゼーションへの注釈の付与やビジュアライゼーションの明確化をおこなうことができます。テキストコールアウト、矢印、画像および色分けの追加によってデータを強調および明確化したうえで、他のユーザーと共有できます。

Data Workbenchでは、特定の解析タスクに対して表示する画層を選択できます。

## Geography プロファイルレイヤー {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

この [!DNL Geography] プロファイルには、デフォルトの画像レイヤーのセットが用意されています。これらのレイヤーは、Data Workbenchサーバーのインストールディレクトリ内の Profiles\Geography\Maps フォルダーに保存されています。

* **[!UICONTROL Blue Marble 2km]:** この地形画像レイヤーは、ワークスペースにグローブビジュアライゼーションを追加すると表示される、世界の 3D マップを作成します。 このレイヤーが選択されていない場合、グローブは表示されませんが、他のレイヤーは表示されます。この [!DNL Blue Marble 2km.layer] ファイルは、 [!DNL Blue Marble 2km.tsi] ファイル。

* **[!UICONTROL Zip Points]:** この要素ポイントレイヤーを使用すると、米国の郵便番号を使用して、データセット内の場所をマッピングできます。 [!DNL Zip Points.txt] ルックアップファイル（Adobe が提供）には、米国のすべての郵便番号と各郵便番号の緯度と経度のリストが含まれています。この [!DNL Zip Points.layer] ファイルは、 [!DNL Zip Points.txt] ファイルと [!DNL Zipcode.dim] ファイルに含まれ、グローブ上の場所の表示に必要な設定パラメーターが含まれます。 データセット内で定義する郵便番号のディメンション（[!DNL Zipcode.dim]）の各要素は、[!DNL Zip Points.txt] ルックアップファイルに記載されている、その郵便番号の緯度と経度を使用してグローブ上にマッピングされます。

   ディメンションの定義について詳しくは、『*データセット設定ガイド*』を参照してください。

* **[!UICONTROL Boundaries]:** このベクトル層は、国などの主要な世界の政治的境界と、湖や島々などの地球の自然な物理的特徴の境界を提供します。 この [!DNL Boundaries.layer] ファイルが 1 つ以上の [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec]、および [!DNL world boundaries.vec] ファイル。

* **[!UICONTROL IP Coordinates]:** この要素ポイントレイヤーでは、動的ポイントを使用して、IP アドレスを使用してデータセット内の場所をマッピングできます。 [!DNL IP Coordinates.layer] ファイルでは、座標のディメンション（[!DNL Coordinates.dim]）を参照します。また、各座標のグローブ上のポイントのサイズを決定する際に使用する指標として、Visitors 指標を指定します。

[!UICONTROL NL Geography] プロファイルや、ご使用のインストール内の他のプロファイルには、ほかにも Adobe が提供した画像レイヤーやお客様の会社が作成した画像レイヤーが含まれている場合があります。

## 新しい画層を作成 {#section-b5313773316c4e0fa748f7376a8e7f0b}

新しい画像レイヤーを作成するには、 [!DNL Geography] プロファイルを任意の Profiles\*profile name*\Maps フォルダーに追加し、必要に応じてファイルの名前を変更して編集します。 新しいレイヤーはすべて、以下の要件を満たす必要があります。

* この [!DNL .layer] ファイルは、サポートされている画層タイプの 1 つの形式に従う必要があります。
* この [!DNL .layer] ファイルは、必要に応じて、適切なルックアップファイルとディメンションファイルを参照する必要があります。
* 参照される参照ファイルも、Data Workbenchサーバーのインストールディレクトリ内に格納する必要があります。また、そのパスは、 [!DNL .layer] ファイル。

各タイプのレイヤーファイルとその関連ファイルの形式およびパラメーターについて詳しくは、この章の該当するレイヤータイプの節を参照してください。
