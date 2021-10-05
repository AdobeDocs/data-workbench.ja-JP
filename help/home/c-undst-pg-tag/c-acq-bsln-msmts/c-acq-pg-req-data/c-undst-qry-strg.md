---
description: クエリ文字列 (cs-uri-query) は、HTTP のステートレス性のため、Web アプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。
title: クエリ文字列について
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# クエリ文字列について{#understanding-the-query-string}

クエリ文字列 (cs-uri-query) は、HTTP のステートレス性のため、Web アプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。

多くの場合、Web サーバーで [!DNL Sensor] が情報を取得する際に、クエリ文字列に情報が渡される場合があります。 [!DNL Site] では、このような情報を使用して、サイトの真の構造、サイトを通る訪問者のパス、その他の情報を照らすことができます。

一部の動的な Web サイトでは、クエリ文字列内の name=value のペア（変数）が、訪問者が実際にリクエストするページを判断するのに重要です。 このような場合、URL は、次のような構造になる場合があります。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

この例では、実際には PAGENAME が、この URL の要求者に提供されるページを示します。 多くの Web ログ分析ツールやサービスは、サイトの URL のクエリ文字列で発生するクエリ文字列変数に基づいて、サイト運営者がサイト内のページを定義する機能を制限しています。 Data Workbench サーバーと Data Workbench は、このようなクエリ名を使用して一意のページを定義するように設定できます。 多くのシステムでは次の URL が同じページとして解釈されますが、 [!DNL Site] では解釈されないので、この点が重要です。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同様に、サイト開発者やアプリケーションは、多くの場合、リクエストされる実際のページの識別とは関係のない、多くのクエリー文字列変数をサイトの URL に追加します。 次に例を示します。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

この例では、クエリ文字列変数 CAMPAIGN=が URL に追加されています。 この CAMPAIGN 変数は、訪問者がこの URL を選択した原因となったマーケティングキャンペーンを示すために使用されています。 [!DNL Site] 訪問者が閲覧したページの定義とは別にこの CAMPAIGN 情報を使用するように設定できるので、レポートや分析の目的でページのリストに次のような情報が表示されます。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
