---
description: Flatten 変換は文字列ベクトルを受け取って、その各値を個別のフィールドにマッピングします。
solution: Analytics
title: Flatten
topic: Data workbench
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Flatten{#flatten}

Flatten 変換は文字列ベクトルを受け取って、その各値を個別のフィールドにマッピングします。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Default | デフォルト値。条件が満たされたが、ログエントリの入力値が利用できない場合に使用されます。 |  |
| Input | 出力フィールド名にマッピングする文字列値のベクトル。 |  |
| Outputs | 一連の出力フィールド名。 |  |

考慮事項： [!DNL Flatten]

* 入力ベクトルに格納されている値が、定義されている出力フィールドよりも多い場合、その超えた分の入力値は単に破棄されます。
* 入力ベクトルに格納されている値が、定義されている出力フィールドよりも少ない場合、余った出力フィールドにはデフォルト値（定義されている場合）または空の文字列（デフォルト値が定義されていない場合）が割り当てられます。

以下の [!DNL Flatten] 変換は、製品のベクトル（x-products）を受け取って、それらを 4 つのフィールド（x-product1 ～ x-product4）に分離します。

![](assets/cfg_TransformationType_Flatten.png)

入力値に格納されている文字列が B57481、C46355、Z97123 であるとき、出力フィールドには次のように値が格納されます。

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = 空（出力よりも入力の方が多く、デフォルト値が指定されていない）
