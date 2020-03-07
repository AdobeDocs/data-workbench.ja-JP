---
description: Copy 変換は、指定された出力フィールドに入力フィールドの値を単純にコピーするものです。入力フィールドが文字列ベクトルとなる可能性がある場合、出力フィールドの名前は「x-」で始める必要があります。
solution: Analytics
title: Copy
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Copy{#copy}

Copy 変換は、指定された出力フィールドに入力フィールドの値を単純にコピーするものです。入力フィールドが文字列ベクトルとなる可能性がある場合、出力フィールドの名前は「x-」で始める必要があります。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Default | 条件判定が true で、指定されたログエントリから入力値が得られなかった場合に使用されます。 |  |
| Input | コピー元のフィールドの名前。 |  |
| Output | 出力フィールドの名前。 |  |

In this example, which uses fields of data collected from website traffic, the output field, x-purchase-success, is given the literal value of &quot;1&quot; each time cs-uri-stem matches [!DNL /checkout/confirmed.php]. If the [!DNL Condition] is not satisfied (that is, cs-uri-stem does not match [!DNL /checkout/confirmed.php]), x-purchase-success is not changed.

![](assets/cfg_TransformationType_Copy.png)

