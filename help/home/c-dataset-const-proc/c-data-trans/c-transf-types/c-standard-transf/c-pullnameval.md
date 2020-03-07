---
description: PullNameValues 変換は、cs-uri-query フィールドに含まれる値を受け取って、名前と値から成る各ペアを別々の文字列に分離する特殊な処理です。
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

PullNameValues 変換は、cs-uri-query フィールドに含まれる値を受け取って、名前と値から成る各ペアを別々の文字列に分離する特殊な処理です。

名前と値を対にした文字列のまとまり全体が、指定された出力フィールドに文字列ベクトルとして出力されます。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Default | デフォルト値。条件が満たされたが、指定されたログエントリの入力値が利用できない場合に使用されます。 |  |
| Output | 出力文字列の名前。 |  |

次の例に使用されている [!DNL PullNameValues] 変換は、検索フォームの使用状況に関する情報（訪問者によって選択されたボタン、フォームに入力された値など）を捕捉するものです。この例では、条件( [!DNL String Match] 「条件」を [参照](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md))を使用して、この変換の使用をページのみに分離しています [!DNL /search.php]。 名前と値のペアのベクトルが、x-search-namevalues フィールドに出力されます。

![](assets/cfg_TransformationType_PullNameValues.png)

Using the transformation as defined above, if the cs-uri-stem field matched the page [!DNL /search.php] and cs-uri-query contained the following:

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

この場合、x-search-namevalues には、次の 3 つの文字列から成るベクトルが格納されます。

* Searchfor=Bob
* State=Virginia
* isMale=true

