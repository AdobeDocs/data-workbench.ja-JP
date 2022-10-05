---
description: クエリ文字列 (cs-uri-query) は、HTTP のステートレス性を考慮して、Web アプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。
title: クエリ文字列について
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 2%

---

# クエリ文字列について{#understanding-the-query-string}

{{eol}}

クエリ文字列 (cs-uri-query) は、HTTP のステートレス性を考慮して、Web アプリケーションやサイト開発者がページ間で情報を渡す際によく使用されます。

多くの場合、情報は、 [!DNL Sensor] Web サーバーで このような情報は、 [!DNL Site] サイトの真の構造、サイトを通る訪問者のパス、その他の情報を照らします。

一部の動的な Web サイトでは、訪問者が実際にリクエストするページを判断するには、クエリ文字列内の name=value のペア（変数）が重要です。 このような場合、URL は、次のような構造になっている場合があります。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

この例では、実際に PAGENAME が、この URL のリクエスタに提供されるページを示します。 多くの Web ログ分析ツールやサービスは、サイトの URL のクエリ文字列で発生するクエリ文字列変数に基づいて、サイト運営者がサイト内のページを定義する機能を制限しています。 Data Workbench サーバーと Data Workbench は、このようなクエリ名を使用して一意のページを定義するように設定できます。 多くのシステムでは次の URL を同じページとして解釈するので、これは重要ですが [!DNL Site] は実行しません。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
https://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

同様に、サイトの開発者やアプリケーションは、多くの場合、リクエストされている実際のページの識別とは関係のない、サイトの URL に多数のクエリー文字列変数を追加します。 次に例を示します。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
https://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

この例では、クエリ文字列変数 CAMPAIGN=が URL に追加されています。 この CAMPAIGN 変数は、訪問者がこの URL を選択する原因となったマーケティングキャンペーンを示すために使用されています。 [!DNL Site] このキャンペーン情報を使用するように設定できますが、訪問者が閲覧したページの定義とは切り離して、レポートや分析のためにページのリストで次のように見えるようにすることができます。

```
https://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
