---
description: Copy 変換は、指定された出力フィールドに入力フィールドの値を単純にコピーするものです。入力フィールドが文字列ベクトルとなる可能性がある場合、出力フィールドの名前は「x-」で始める必要があります。
title: コピー
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 76%

---

# コピー{#copy}

{{eol}}

Copy 変換は、指定された出力フィールドに入力フィールドの値を単純にコピーするものです。入力フィールドが文字列ベクトルとなる可能性がある場合、出力フィールドの名前は「x-」で始める必要があります。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）。変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | 条件判定が true で、指定されたログエントリから入力値が得られなかった場合に使用されます。 |  |
| Input | コピー元のフィールドの名前。 |  |
| 出力 | 出力フィールドの名前。 |  |

この例では、Web サイトトラフィックから収集されたデータのフィールドを使用し、cs-uri-stem が一致するたびに、出力フィールド x-purchase-success にリテラル値「1」が与えられます [!DNL /checkout/confirmed.php]. この [!DNL Condition] が満たされていない（つまり、cs-uri-stem が一致しない） [!DNL /checkout/confirmed.php]) の代わりに x-purchase-success を使用する場合、x-purchase-success は変更されません。

![](assets/cfg_TransformationType_Copy.png)
