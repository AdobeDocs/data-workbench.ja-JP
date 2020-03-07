---
description: 数式の構文ルールです。
solution: Analytics
title: 任意の式の構文
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax for any expression{#syntax-for-any-expression}

数式の構文ルールです。

* 式の中では、キーワードは大文字と小文字の区別があり、表示どおりに正確に入力する必要があります。
* 式の中では、スペースを含む指標名、ディメンション名およびフィルター名には、単語の間にアンダースコアを使用する必要があります。次に例を示します。[!DNL Page_Views]
* 式の中の文字列では、特定の一重引用符、二重引用符およびバックスラッシュにエスケープが必要です。次に例を示します。

   * [!DNL “can’t”] が有効で、エスケープする必要はありませんが、受け入れら [!DNL ‘can’t’] れず、エスケープする必要がありま [!DNL ‘can\’t’]す。

   * [!DNL c:\windows] は、としてエスケープする必要があり [!DNL c:\\windows]ます。

