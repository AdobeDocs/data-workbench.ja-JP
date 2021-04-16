---
description: クエリ文字列(cs-uri-クエリ)は、HTTPのステートレスな特性を持つので、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。
title: クエリ文字列について
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# クエリ文字列について{#understanding-the-query-string}

クエリ文字列(cs-uri-クエリ)は、HTTPのステートレスな特性を持つので、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。

多くの場合、Webサーバーで[!DNL Sensor]が情報を取得したときに、クエリ文字列に情報が渡されます。 このような情報は、[!DNL Site]がサイトの真の構造や、サイトを通る訪問者のパス、その他の情報を照らすのに使用できます。

一部の動的なWebサイトでは、訪問者がリクエストする実際のページを決定するために、クエリ文字列内のname=valueのペア（変数）が重要です。 このような場合、URLは次のように構造化されているか、類似した方法で表示されます。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

この例では、PAGENAMEは実際に、このURLの要求者にどのページが提供されるかを示すインジケータです。 多くのWebログ分析ツールやサービスでは、サイトのURLのクエリ文字列で発生するクエリ文字列変数に基づいて、サイト運営者がサイトのどのページを定義するかを制限しています。 Data WorkbenchサーバーおよびData Workbenchは、このようなクエリ名を使用して一意のページを定義するように設定できます。 多くのシステムでは次のURLが同じページとして解釈されますが、[!DNL Site]では解釈されないので、これは重要です。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同様に、サイト開発者やアプリケーションは、多くの場合、リクエストされる実際のページの識別とは無関係なクエリ文字列変数をサイトのURLに追加します。 次に例を示します。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

この例では、クエリ文字列変数キャンペーン=がURLに追加されています。 このキャンペーン変数は、訪問者がこのURLを選択した原因となったマーケティングキャンペーンを示すために使用されます。 [!DNL Site] は、このキャンペーン情報を使用するように設定できますが、訪問者が閲覧したページの定義とは切り離して、レポートや分析を目的としたページのリストに次のように表示されるようにします。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
