---
description: クエリ文字列(cs-uri-query)は、HTTPのステートレスな性質上、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。
solution: Analytics
title: クエリ文字列について
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# クエリ文字列について{#understanding-the-query-string}

クエリ文字列(cs-uri-query)は、HTTPのステートレスな性質上、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。

多くの場合、Webサーバーで取得した情報がクエリ文字列に渡さ [!DNL Sensor] れる可能性があります。 このような情報は、サイトの真の構 [!DNL Site] 造、サイトを通る訪問者のパス、およびその他の情報を照らすために使用できます。

一部の動的なWebサイトでは、訪問者が実際にリクエストするページを決定する際に、クエリ文字列内のname=valueのペア（変数）が重要です。 この場合、URLは次のような方法で構造化されます。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

この例では、PAGENAMEは実際に、このURLの要求者にどのページが提供されるかを示すインジケーターです。 多くのWebログ分析ツールやサービスでは、サイトのURLのクエリ文字列で発生するクエリ文字列変数に基づいて、サイト運営者がサイト内のページを定義する機能を制限しています。 Data WorkbenchサーバーおよびData Workbenchは、このようなクエリー名を使用して一意のページを定義するように設定できます。 多くのシステムでは、次のURLが同じページとして解釈されますが、解釈されないので、この [!DNL Site] 方法が重要です。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同様に、サイト開発者やアプリケーションは、多くの場合、リクエストされる実際のページの識別とは関係ない、多くのクエリ文字列変数をサイトのURLに追加します。 以下に例を示します。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

この例では、クエリ文字列変数CAMPAIGN=がURLに追加されています。 このCAMPAIGN変数は、訪問者がこのURLを選択したマーケティングキャンペーンを示すために使用されています。 [!DNL Site] このキャンペーン情報を使用するように設定できますが、訪問者が閲覧したページの定義とは別に、レポートや分析の目的でページのリストに次の情報が表示されるようにします。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

