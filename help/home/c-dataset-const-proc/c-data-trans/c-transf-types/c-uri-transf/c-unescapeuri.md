---
description: UnescapeURI 変換は、文字列の中のエスケープされたすべての文字のエスケープを解除します。
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 93%

---

# UnescapeURI{#unescapeuri}

{{eol}}

UnescapeURI 変換は、文字列の中のエスケープされたすべての文字のエスケープを解除します。

>[!NOTE]
>
>エスケープ文字は、URI 文字列内の安全でない文字に置き換えられます。 エスケープ文字は、パーセント記号に続く 2 桁の 16 進数で表されます（例：%20）。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）。変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | デフォルト値。条件が満たされたが、入力値が利用できない場合に使用されます。 |  |
| Input | エスケープを解除する URI 文字列。 |  |
| 出力 | エスケープ解除済みの文字列を格納するフィールドの名前。 |  |

次の変換は、HTTP ヘッダーフィールド内の docname 値のエスケープを解除し、出力結果を x-docname-unescaped フィールドに格納するものです。

![](assets/cfg_TransformationType_UnescapeURI.png)

docname に次の値が格納されているとします。

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

この場合、x-docname-unescape の値は次のようになります。

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
