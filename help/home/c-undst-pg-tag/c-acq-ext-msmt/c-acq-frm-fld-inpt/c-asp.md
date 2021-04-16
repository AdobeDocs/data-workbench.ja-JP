---
description: Webページは、多くの場合、ASP(Active Server Pages)プログラミング言語を使用して構造化されます。
title: ASP 固有の情報
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP 固有の情報{#asp-specific-information}

Webページは、多くの場合、ASP(Active Server Pages)プログラミング言語を使用して構造化されます。

ASPは、IIS(インターネット情報サービス)内で動作するMicrosoftのテクノロジです。 ブラウザがASPファイルを要求すると、IISはその要求をASPエンジンに渡す。 ASPエンジンは、ASPファイルを1行ずつ読み取り、ファイル内のスクリプトを実行します。 最後に、ASPファイルはプレーンHTMLとしてブラウザに返されます。 ASPは、他の用途に加えて、HTMLフォームから送信されたユーザークエリやデータに対する応答や要求を許可するRESPONDオブジェクトまたはREQUESTオブジェクトを提供します。

フォームに入力した値を、ユーザーのブラウザーのアドレスバーに表示されるURLや、HTMLコード自体で表示可能なURLに追加しないことがあります。 サーバーサイドのシンプルなJavaScriptを使用すると、フォームフィールド名とそれぞれの値を、ユーザーのブラウザー内で利用できるようにしたり、HTMLファイルに埋め込んだりする必要がなく、ログファイルに追加できます。 Webサイト内の特定のフォームに入力された実際のフォーム値を取り込むには、いくつかのコードを追加して、フォーム値をログリクエストに追加する必要があります。

フォームの処理ページ内で、次のコードを含めて、入力したフォーム値を要求データに追加します（また、送信したフォーム値を外部データベースや他の場所に書き込みます）。

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

このプロセスは、[!DNL Form Processing]ページのリクエストデータに定義されたとおりのフォーム値を追加します。 ログデータ内では、下図に示すように、[!DNL Form Processing]ページのクエリ文字列として付加された値を使用できます。 例えば、v_1、v_2、v_3およびv_4は、適切なフォームフィールドに入力されたデータを含むクエリ文字列になります。 上記の例で説明した構文は、取り込む必要のある追加のフォームフィールドと値に対して複製できます。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

すべてのフォームフィールドと値を取り込んで分析に使用する場合は、次の構文を使用できます。

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

次の例では、HTML内に存在するすべてのフォームフィールドとそれぞれの値を取り、[!DNL Form Processing]ページのログエントリにクエリ文字列として追加します。 これには、フォーム内に存在する非表示のフィールドが含まれることに注意してください。

ログデータは、次の表に示すように拡張されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | NAMEクエリ文字列に関連付けられた値 | v_1=John Smith |
| v_2 | CITYクエリ文字列に関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATEクエリ文字列に関連付けられた値 | v_3=カリフォルニア |
| v_4 | ZIPクエリ文字列に関連付けられた値 | v_4=90210 |
