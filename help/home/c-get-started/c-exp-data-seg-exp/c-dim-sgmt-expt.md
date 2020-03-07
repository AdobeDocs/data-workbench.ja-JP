---
description: エクスポートするデータはすべて、プロファイル内でディメンションとして定義する必要があります。
solution: Analytics
title: セグメントエクスポートで使用するディメンションを作成する
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Create dimensions for use with segment export{#create-dimensions-for-use-with-segment-export}

エクスポートするデータはすべて、プロファイル内でディメンションとして定義する必要があります。

ディメンションがまだプロファイルに存在しない場合は、作成する必要があります。以下のいずれかの方法を使用して、ディメンションを作成できます。

* ディメンションを [!DNL Transformation.cfg] ファイルに追加します。 『*データセット設定ガイド*』を参照してください。

* Create a new [!DNL .dim] file. See [Creating and Editing Derived Dimensions](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* プロセスマップやセグメントなどのビジュアライゼーションに選択範囲を作成し、選択範囲をディメンションとして保存します。「 プロセス [マップからのディメンションの保存](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) 、およびセ [グメントディメンションの作成](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)。

追跡 ID や電子メールアドレスなどのデータ（多数の要素を持つことができる）のフィールドをエクスポートするには、データの生の文字列を保存する非正規ディメンションを作成する必要があります。

非正規ディメンションについて詳しくは、『*データセット設定ガイド*』を参照してください。 
