---
description: エクスポートするデータはすべて、プロファイル内でディメンションとして定義する必要があります。
title: セグメントエクスポートで使用するディメンションの作成
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 88%

---

# セグメントエクスポートで使用するディメンションの作成{#create-dimensions-for-use-with-segment-export}

{{eol}}

エクスポートするデータはすべて、プロファイル内でディメンションとして定義する必要があります。

ディメンションがまだプロファイルに存在しない場合は、作成する必要があります。以下のいずれかの方法を使用して、ディメンションを作成できます。

* ディメンションを [!DNL Transformation.cfg] ファイルに追加します。 『*データセット設定ガイド*』を参照してください。

* 新しい [!DNL .dim] ファイル。 詳しくは、 [派生Dimensionの作成と編集](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* プロセスマップやセグメントなどのビジュアライゼーションに選択範囲を作成し、選択範囲をディメンションとして保存します。「 [プロセスマップからDimensionを保存中](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) および [セグメントDimensionの作成](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

追跡 ID や電子メールアドレスなどのデータ（多数の要素を持つことができる）のフィールドをエクスポートするには、データの生の文字列を保存する非正規ディメンションを作成する必要があります。

非正規ディメンションについて詳しくは、『*データセット設定ガイド*』を参照してください。 
