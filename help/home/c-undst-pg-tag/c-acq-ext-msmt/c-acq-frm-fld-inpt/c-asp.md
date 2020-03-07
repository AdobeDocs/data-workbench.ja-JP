---
description: ウェブページは、多くの場合、ASP(Active Server Pages)プログラミング言語を使用して構造化されます。
solution: Analytics
title: ASP固有の情報
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ASP固有の情報{#asp-specific-information}

ウェブページは、多くの場合、ASP(Active Server Pages)プログラミング言語を使用して構造化されます。

ASPは、IIS（インターネットインフォメーションサービス）内で動作するMicrosoftのテクノロジーです。 ブラウザがASPファイルを要求すると、IISはASPエンジンに要求を渡す。 ASPエンジンは、ASPファイルを1行ずつ読み取り、ファイル内のスクリプトを実行する。 最後に、ASPファイルはプレーンHTMLとしてブラウザに返されます。 ASPは、他の用途に加えて、HTMLフォームから送信されたユーザークエリやデータの応答や要求を許可するRESPONDまたはREQUESTオブジェクトを提供します。

フォームに入力した値を、ユーザーのブラウザーのアドレスバーに表示されるURLや、HTMLコード自体で表示可能なURLに追加しない場合があります。 サーバーサイドのシンプルなJavaScriptを使用すると、フォームフィールド名とそれぞれの値をログファイルに追加できます。ユーザーのブラウザー内で使用できるようにしたり、HTMLファイルに埋め込んだりする必要はありません。 Webサイト内の特定のフォームに入力された実際のフォーム値を取り込むには、数行のコードを追加して、フォーム値をログ要求に追加する必要があります。

フォームの処理ページ内で、次のコードを含めて、入力したフォーム値を要求データに追加します（送信したフォーム値を外部データベースや他の場所に書き込むのに加えて）。

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

このプロセスでは、ページのリクエストデータに定義されたとおりにフォーム値が追加さ [!DNL Form Processing] れます。 ログデータ内では、後述のように、ページのクエリ文字列として追加された値 [!DNL Form Processing] が使用できます。 例えば、v_1、v_2、v_3、v_4は、適切なフォームフィールドに入力されたデータを含むクエリ文字列になります。 上記の例で説明した構文は、取り込む追加のフォームフィールドと値に対して複製できます。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

すべてのフォームフィールドと値を取得し、分析に使用する場合は、次の構文を使用できます。

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

次の例では、HTML内に存在するすべてのフォームフィールドとそれぞれの値を取り込み、クエリ文字列としてページのログエントリに追加 [!DNL Form Processing] します。 この場合、フォーム内に存在する非表示のフィールドが含まれることに注意してください。

ログデータは、次の表に示すように拡張されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | NAMEクエリ文字列に関連付けられた値 | v_1=John Smith |
| v_2 | CITYクエリ文字列に関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATEクエリ文字列に関連付けられた値 | v_3=カリフォルニア |
| v_4 | ZIPクエリ文字列に関連付けられた値 | v_4=90210 |

