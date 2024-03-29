---
description: Hash 変換は、入力値からほぼ一意の 64 ビット数値を表す文字列を作成します。
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 83%

---

# Hash{#hash}

{{eol}}

Hash 変換は、入力値からほぼ一意の 64 ビット数値を表す文字列を作成します。

この変換に同じ入力値を与えると常に同じハッシュ値が作成されます。

>[!NOTE]
>
>変換ではハッシュ値の可能な領域として 64 ビットの数値が使用されるので、結果の値はほぼ一意です。 重複のない 100 万件の入力データを [!DNL hash] 変換に与えたとき、ハッシュ値の衝突が起こる確率は 38,000,000 回に 1 回です。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）。変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | 入力値が利用できない場合に使用されるデフォルト値。 |  |
| Inputs | ハッシュ値の作成に使用する一連の入力値。 |  |
| 出力 | 出力用フィールドの名前。 |  |

次の例では、c-ip フィールドの値と cs(user-agent) フィールドの値を使用して追跡 ID を作成し、それを x-trackingid フィールドに格納します。

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>この例は、一意のトラッキング ID を作成するのに最適なソリューションではありません。 しかし、長期保存用のログ情報が使われている状況では、きわめて効果的な方法である場合があります。
