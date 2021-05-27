---
description: 数式の構文ルールです。
title: 式の構文
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
exl-id: ca1a52c1-b5bd-48bd-95cd-f8059913bd0a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 77%

---

# 式の構文{#syntax-for-any-expression}

数式の構文ルールです。

* 式の中では、キーワードは大文字と小文字の区別があり、表示どおりに正確に入力する必要があります。
* 式の中では、スペースを含む指標名、ディメンション名およびフィルター名には、単語の間にアンダースコアを使用する必要があります。例：[!DNL Page_Views]
* 式の中の文字列では、特定の一重引用符、二重引用符およびバックスラッシュにエスケープが必要です。次に例を示します。

   * [!DNL “can’t”] は有効で、エスケープする必要はありませんが、受け入れ [!DNL ‘can’t’] られないので、エスケープする必要がありま [!DNL ‘can\’t’]す。

   * [!DNL c:\windows] は、とエスケープする必要があり [!DNL c:\\windows]ます。
