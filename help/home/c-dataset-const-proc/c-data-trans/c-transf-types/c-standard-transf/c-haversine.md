---
description: Haversine（半正矢）式とは、緯度と経度から特定される球体上の 2 点間の大圏距離を導く数式です。
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

Haversine（半正矢）式とは、緯度と経度から特定される球体上の 2 点間の大圏距離を導く数式です。

Like the formula, the [!DNL Haversine] transform requires two sets of [!DNL Latitude] and [!DNL Longitude] settings, using these four inputs to calculate the true distance across the Earth between two locations.

この距離は、「In Kilometers」フラグを（false または true に）変更することによってマイルまたはキロメートルで表すことができます。

![](assets/cfg_TransformationType_Haversine.png)

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Latitude 1 Field | 地点 1 の緯度。 |  |
| Latitude 2 Field | 地点 2 の緯度。 |  |
| Longitude 1 Field | 地点 1 の経度。 |  |
| Longitude 2 Field | 地点 2 の経度。 |  |
| Output | 計算後、ディメンションのエレメントとして指定された地点間の距離が [!DNL Output] フィールドに格納されます。 |  |

例えば、店舗の緯度と経度を Lat1 および Lon1 としてコーディングしておけば、IP ルックアップで顧客の緯度と経度を求めることによって、最も多くの顧客が商品を購入する（または来店する）店舗までの距離を調べることができます。

>[!NOTE]
>
>他の場所の距離を識別する場合は、それぞれの場所に、緯度と経度のフィールドのセットが必要です。

