---
description: Tokenize 変換は、入力文字列に対して反復的に正規表現を適用します。
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 89%

---

# Tokenize{#tokenize}

{{eol}}

Tokenize 変換は、入力文字列に対して反復的に正規表現を適用します。

ただし、 [!DNL RETransform], [!DNL Tokenize] は、文字列全体と一致する必要はありません。次に使用する正規表現 [!DNL Tokenize] 変換は、入力のサブセットに一致させることができます。 [!DNL Tokenize] は、一致が見つかった後、最後の一致に続く文字から再度、正規表現を適用します。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Case Sensitive | true または false。マッチングで大文字と小文字を区別するかどうかを指定します。 |  |
| コメント | （オプション）。変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | デフォルト値。条件が満たされたが、入力値が利用できない場合、または正規表現が入力値と一致しない場合に使用されます。 |  |
| 式 | マッチングに使用する正規表現。 |  |
| Outputs | 出力文字列の名前。特定の入力文字列から複数の出力結果を得ることができます。出力結果の数は、正規表現で捕捉するサブパターンの数に相当します。 |  |

次の例では、[!DNL Tokenize] 変換の正規表現を使用してクエリー文字列（cs-uri-query）の名前を捕捉し、得られたサブパターン（クエリー名）を x-pull-query-name に出力しています。

![](assets/cfg_TransformationType_Tokenize.png)

クエリー文字列が「a=b&amp;c=d」であるとき、出力結果は「a」と「c」から成るベクトルになります。

正規表現について詳しくは、 [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
