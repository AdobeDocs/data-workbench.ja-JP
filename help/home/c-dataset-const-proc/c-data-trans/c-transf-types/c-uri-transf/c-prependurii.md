---
description: PrependURI 変換は、AppendURI 変換と同様、URI ディメンションを構築するときに Data Workbench サーバーで使用される内部フィールドに作用します。
title: PrependURI
uuid: 3f2fb1a7-83f7-481e-b892-0937acd379f9
exl-id: c39d9241-ed66-446e-b59d-fdb11942d0e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 100%

---

# PrependURI{#prependuri}

PrependURI 変換は、AppendURI 変換と同様、URI ディメンションを構築するときに Data Workbench サーバーで使用される内部フィールドに作用します。

[!DNL PrependURI] 変換は、URI に含まれている値の前に、指定された入力フィールドの値を追加します。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| 名前 | 変換のわかりやすい名前。ここには任意の名前を入力することができます。 |  |
| コメント | （オプション）変換についてのメモ。 |  |
| 条件 | この変換が適用される条件。 |  |
| デフォルト | デフォルト値。条件が満たされたが、入力値が利用できない場合に使用されます。 |  |
| Input | URI の先頭に付加する値のフィールド名。 |  |

次の例は、URI の先頭に s-dns フィールドを単純に付加します。クライアントデバイスからリクエストされたドメインを含める形で URI ディメンションの情報を補います。

![](assets/cfg_TransformationType_PrependURI.png)

この例で、次の URI の先頭に s-dns フィールドを付加するとします。

* [!DNL /modelview.asp&id=login]

この場合、次の URL が得られます。

* [!DNL www.adobe.com/modelview.asp?id=login]

リクエストされたドメインが URI に追加されました。
