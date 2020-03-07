---
description: ReplaceURI 変換は、内部 URI ディメンション内の値を新しい値に変更します。
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

ReplaceURI 変換は、内部 URI ディメンション内の値を新しい値に変更します。

[!DNL URI Prefix] を指定した場合、与えられた入力値と URI プレフィックスが単に連結された値が生成されます。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| Comments | (オプション)変換についてのメモ。 |  |
| Condition | この変換が適用される条件。 |  |
| Default | デフォルト値。条件が満たされたが、入力値が利用できない場合に使用されます。 |  |
| Input | URI を置き換える値。 |  |
| URI Prefix | [!DNL Input] フィールドの値の先頭に付加する値（文字列）。 |  |

>[!NOTE]
>
>Before applying [!DNL ReplaceURI] transformations, you should create a new simple dimension with a parent of [!DNL Page View]from a copy of cs-uri-stem or cs-uri. これに関して不明な点がありましたらアドビにお問い合わせください。

この例では、「page=[!DNL ReplaceURI]pageid *」というクエリー文字列の* pageid[!DNL homepage.html] で示される閲覧ページが、Web サイトのホームページであった場合、*を使用して、すべて「*」に置き換えます。その結果、より見やすい形式の URI が得られます。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

ここに示した変換を次のページに適用したとします。

* [!DNL www.examplesite.com/info.html?page=1550]

この場合、次のように変換されます。

* [!DNL www.examplesite.com/homepage.html]

