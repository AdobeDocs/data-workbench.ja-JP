---
description: Data Workbench Geography は、すべての地形画像レイヤーソースに対して、緯度 — 経度投影法とユニバーサル横メルカトル (UTM) 投影法の両方をサポートしています。
title: 地形画像の投影情報の指定
uuid: 4a476192-e749-4187-b64e-9794f39b0019
exl-id: 400b9b59-f700-4b16-8549-fe93140cad1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 65%

---

# 地形画像の投影情報の指定{#specifying-projection-information-for-terrain-images}

{{eol}}

Data Workbench Geography は、すべての地形画像レイヤーソースに対して、緯度 — 経度投影法とユニバーサル横メルカトル (UTM) 投影法の両方をサポートしています。

投影情報は、生の未投影ビットマップおよび未投影の一般的な画像に必要です。埋め込み投影情報を使用して画像の投影情報を指定できますが、投影のパラメーターは画像自体に埋め込まれている測地データから自動的に決定されるので、通常その必要はありません。以降の節では、以下の投影形式を [!DNL Terrain Images.cfg] ファイルで指定する方法について詳しく説明します。
