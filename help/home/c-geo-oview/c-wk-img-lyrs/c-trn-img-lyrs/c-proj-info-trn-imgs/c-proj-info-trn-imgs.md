---
description: Data Workbenchの地域は、すべての地形画像レイヤーソースに対して、緯度 — 経度投影法とユニバーサル横メルカトル(UTM)投影法の両方をサポートしています。
solution: Analytics
title: 地形画像の投影情報の指定
topic: Data workbench
uuid: 4a476192-e749-4187-b64e-9794f39b0019
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 地形画像の投影情報の指定{#specifying-projection-information-for-terrain-images}

Data Workbenchの地域は、すべての地形画像レイヤーソースに対して、緯度 — 経度投影法とユニバーサル横メルカトル(UTM)投影法の両方をサポートしています。

投影情報は、生の未投影ビットマップおよび未投影の一般的な画像に必要です。埋め込み投影情報を使用して画像の投影情報を指定できますが、投影のパラメーターは画像自体に埋め込まれている測地データから自動的に決定されるので、通常その必要はありません。以降の節では、以下の投影形式を [!DNL Terrain Images.cfg] ファイルで指定する方法について詳しく説明します。
