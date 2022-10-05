---
description: ReplaceURI 変換は、内部 URI ディメンション内の値を新しい値に変更します。
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 88%

---

# ReplaceURI{#replaceuri}

{{eol}}

ReplaceURI 変換は、内部 URI ディメンション内の値を新しい値に変更します。

[!DNL URI Prefix] を指定した場合、与えられた入力値と URI プレフィックスが単に連結された値が生成されます。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）。変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | デフォルト値。条件が満たされたが、入力値が利用できない場合に使用されます。 |  |
| Input | URI を置き換える値。 |  |
| URI Prefix | [!DNL Input] フィールドの値の先頭に付加する値（文字列）。 |  |

>[!NOTE]
>
>適用する前に [!DNL ReplaceURI] 変換を行う場合は、次の親を持つ新しいシンプルディメンションを作成する必要があります： [!DNL Page View]cs-uri-stem または cs-uri のコピーから。 これに関して不明な点がありましたらアドビにお問い合わせください。

この例では、「page=[!DNL ReplaceURI]pageid *」というクエリー文字列の* pageid[!DNL homepage.html] で示される閲覧ページが、Web サイトのホームページであった場合、*を使用して、すべて「*」に置き換えます。その結果、より見やすい形式の URI が得られます。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

ここに示した変換を次のページに適用したとします。

* [!DNL www.examplesite.com/info.html?page=1550]

この場合、次のように変換されます。

* [!DNL www.examplesite.com/homepage.html]
