---
description: 数式の構文ルールです。
title: 式の構文
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 77%

---

# 式の構文{#syntax-for-any-expression}

{{eol}}

数式の構文ルールです。

* 式の中では、キーワードは大文字と小文字の区別があり、表示どおりに正確に入力する必要があります。
* 式の中では、スペースを含む指標名、ディメンション名およびフィルター名には、単語の間にアンダースコアを使用する必要があります。例：[!DNL Page_Views]
* 式の中の文字列では、特定の一重引用符、二重引用符およびバックスラッシュにエスケープが必要です。次に例を示します。

   * [!DNL “can’t”] は使用可能で、エスケープする必要はありませんが、 [!DNL ‘can’t’] が許容できず、次のようにエスケープする必要があります： [!DNL ‘can\’t’].

   * [!DNL c:\windows] は [!DNL c:\\windows].
