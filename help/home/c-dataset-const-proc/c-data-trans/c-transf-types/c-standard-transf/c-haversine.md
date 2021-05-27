---
description: Haversine（半正矢）式とは、緯度と経度から特定される球体上の 2 点間の大圏距離を導く数式です。
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 79%

---

# Haversine{#haversine}

Haversine（半正矢）式とは、緯度と経度から特定される球体上の 2 点間の大圏距離を導く数式です。

この式と同様に、[!DNL Haversine]変換には[!DNL Latitude]と[!DNL Longitude]の2組の設定が必要です。これらの4つの入力を使用して、2つの場所の間の地球の真の距離を計算します。

この距離は、「In Kilometers」フラグを（false または true に）変更することによってマイルまたはキロメートルで表すことができます。

![](assets/cfg_TransformationType_Haversine.png)

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| Latitude 1 Field | 地点 1 の緯度。 |  |
| Latitude 2 Field | 地点 2 の緯度。 |  |
| Longitude 1 Field | 地点 1 の経度。 |  |
| Longitude 2 Field | 地点 2 の経度。 |  |
| Output | 計算後、ディメンションのエレメントとして指定された地点間の距離が [!DNL Output] フィールドに格納されます。 |  |

例えば、店舗の緯度と経度を Lat1 および Lon1 としてコーディングしておけば、IP ルックアップで顧客の緯度と経度を求めることによって、最も多くの顧客が商品を購入する（または来店する）店舗までの距離を調べることができます。

>[!NOTE]
>
>他の場所の距離を識別する場合は、それぞれの場所に、緯度と経度のフィールドが独自に設定されている必要があります。
