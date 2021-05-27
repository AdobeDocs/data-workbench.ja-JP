---
description: クエリ文字列(cs-uri-query)は、HTTPのステートレス性を考慮して、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。
title: クエリ文字列について
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# クエリ文字列について{#understanding-the-query-string}

クエリ文字列(cs-uri-query)は、HTTPのステートレス性を考慮して、Webアプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。

多くの場合、[!DNL Sensor]がWebサーバーで情報を取得する際に、クエリー文字列に情報が渡される場合があります。 [!DNL Site]は、このような情報を使用して、サイトの真の構造と、サイトを通る訪問者のパス、その他の情報を照らすことができます。

一部の動的なWebサイトでは、訪問者が実際にリクエストするページを判断するために、クエリ文字列内のname=valueのペア（変数）が重要です。 このような場合、URLは、次のような構造になります。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

この例では、実際にPAGENAMEが、このURLの要求者に提供されるページのインジケーターです。 多くのWebログ分析ツールやサービスは、サイトのURLのクエリ文字列で発生するクエリ文字列変数に基づいて、サイトのオペレーターがサイト内のページを定義する機能を制限します。 Data WorkbenchサーバーとData Workbenchは、このようなクエリ名を使用して一意のページを定義するように設定できます。 多くのシステムでは次のURLが同じページとして解釈されますが、 [!DNL Site]では解釈されないので、これは重要です。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同様に、サイト開発者やアプリケーションは、多くの場合、リクエストされる実際のページを識別するのとは関係のない、サイトのURLに多くのクエリー文字列変数を追加します。 以下に例を示します。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

この例では、クエリ文字列変数CAMPAIGN=がURLに追加されています。 このCAMPAIGN変数は、訪問者がこのURLを選択した原因となったマーケティングキャンペーンを示すために使用されます。 [!DNL Site] このキャンペーン情報を使用するように設定できますが、訪問者が閲覧したページの定義とは切り離して、レポートや分析のためにページのリストで次のように表示できます。

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
