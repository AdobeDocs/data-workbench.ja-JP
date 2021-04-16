---
description: PullNameValues 変換は、cs-uri-query フィールドに含まれる値を受け取って、名前と値から成る各ペアを別々の文字列に分離する特殊な処理です。
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 84%

---

# PullNameValues{#pullnamevalues}

PullNameValues 変換は、cs-uri-query フィールドに含まれる値を受け取って、名前と値から成る各ペアを別々の文字列に分離する特殊な処理です。

名前と値を対にした文字列のまとまり全体が、指定された出力フィールドに文字列ベクトルとして出力されます。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | デフォルト値。条件が満たされたが、指定されたログエントリの入力値が利用できない場合に使用されます。 |  |
| Output | 出力文字列の名前。 |  |

次の例に使用されている [!DNL PullNameValues] 変換は、検索フォームの使用状況に関する情報（訪問者によって選択されたボタン、フォームに入力された値など）を捕捉するものです。この例では、[!DNL String Match]条件（[条件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)を参照）を使用して、この変換の使用を[!DNL /search.php]ページのみに分離しています。 名前と値のペアのベクトルが、x-search-namevalues フィールドに出力されます。

![](assets/cfg_TransformationType_PullNameValues.png)

上述の変換を使用した場合、cs-uri-stemフィールドが[!DNL /search.php]ページと一致し、cs-uri-クエリに次の内容が含まれているとします。

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

この場合、x-search-namevalues には、次の 3 つの文字列から成るベクトルが格納されます。

* Searchfor=Bob
* State=Virginia
* isMale=true
