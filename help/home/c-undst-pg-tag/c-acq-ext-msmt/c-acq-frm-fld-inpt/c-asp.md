---
description: Web ページは、多くの場合、ASP(Active Server Pages) プログラミング言語を使用して構造化されます。
title: ASP 固有の情報
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP 固有の情報{#asp-specific-information}

{{eol}}

Web ページは、多くの場合、ASP(Active Server Pages) プログラミング言語を使用して構造化されます。

ASP は、IIS（インターネットインフォメーションサービス）内で動作するMicrosoftテクノロジーです。 ブラウザが ASP ファイルを要求すると、IIS はその要求を ASP エンジンに渡します。 ASP エンジンは、ASP ファイルを 1 行ずつ読み取り、ファイル内のスクリプトを実行します。 最後に、ASP ファイルがプレーンHTMLとしてブラウザに返されます。 ASP は、RESPONS または REQUEST オブジェクトを提供し、他の用途に加えて、HTML・フォームから送信されたユーザー・クエリやデータの応答または要求を許可します。

場合によっては、ユーザーのブラウザーのアドレスバー内に表示される URL や、HTMLコード自体に表示可能な URL に、フォームに入力された値を追加したくないことがあります。 単純なサーバー側 JavaScript を使用すると、フォームフィールド名とそれぞれの値を、ユーザーのブラウザー内で使用できるようにしたり、HTMLファイルに埋め込んだりすることなく、ログファイルに追加できます。 Web サイト内の特定のフォームに入力された実際のフォーム値を取り込むには、数行のコードを追加して、フォーム値をログリクエストに追加する必要があります。

フォームの処理ページ内で、次のコードを追加して、入力したフォームの値を（送信したフォームの値を外部データベースやその他の場所に書き込むのに加えて）要求データに追加します。

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

このプロセスは、 [!DNL Form Processing] ページ。 ログデータ内では、追加された値が [!DNL Form Processing] ページを次の図のように編集します。 例えば、v_1、v_2、v_3 および v_4 は、適切なフォームフィールドに入力されたデータを含むクエリ文字列になります。 上記の例で説明した構文は、取り込む追加のフォームフィールドおよび値に対して複製できます。

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

すべてのフォームフィールドと値を取り込んで分析に使用する場合は、次の構文を使用できます。

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

この例では、HTML内に存在するすべてのフォームフィールドとそれぞれの値を取り込み、クエリ文字列として [!DNL Form Processing] ページ。 これには、フォーム内に存在する非表示のフィールドが含まれることに注意してください。

ログデータは、次の表で詳しく説明するように拡張されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | NAME クエリ文字列に関連付けられた値 | v_1=John Smith |
| v_2 | CITY クエリ文字列に関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATE クエリ文字列に関連付けられた値 | v_3=カリフォルニア |
| v_4 | ZIP クエリ文字列に関連付けられた値 | v_4=90210 |
