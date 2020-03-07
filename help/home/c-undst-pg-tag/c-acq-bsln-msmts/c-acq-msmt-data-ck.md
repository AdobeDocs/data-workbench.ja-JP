---
description: Sensorは、収集されたベースライン測定データの一部として、訪問者のコンピューターからWebサーバーからリクエストを行う際に送信されたドメインcookieを収集します。
solution: Analytics
title: cookieを使用した測定データの取得
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# cookieを使用した測定データの取得{#acquiring-measurement-data-through-cookies}

Sensorは、収集されたベースライン測定データの一部として、訪問者のコンピューターからWebサーバーからリクエストを行う際に送信されたドメインcookieを収集します。

これには、訪問者がシステムとやり取りする際にWebサイトで設定される永続的なCookieとセッションCookieの両方が含まれます。

ほとんどの場合、Webサイトは訪問者を識別するために永続的なcookieを設定し、以降の訪問者セッションで使用するためのユーザー入力を取り込みます。 永続的なcookieに書き込まれ、保存される情報は、Data Workbenchサーバー内の他のすべての測定データと共に取得して使用できます。

このような永続的なcookieの例としては、訪問者のコンピューター上に存在するドメイン固有のcookie内に存在する数値キーの形で顧客識別子が関与する場合があります。 訪問者を再訪問者として識別するだけでなく、永続的なcookieを使用して訪問者を再訪問者としてさらに識別したり、訪問者を顧客データベース内の情報に結び付けて、オフライン顧客人口統計情報を内に表示し、インタラクティブな分析に使用したりできます。 [!DNL Site]

セッションcookieは、フォームフィールドやWebサイト内の他の動的なインタラクティブ要素を介してユーザー入力を収集するための良いメカニズムです。 ユーザー固有の入力データを取り込むためのフォームを実装するWebサイトの場合、セッションがアクティブである限り、情報はセッションcookieに残ります。 ユーザーがWebサイトを離れたり、セッションを終了したりすると、その情報はユーザーのコンピューターに保存されなくなります。 ただし、入力された情報はによって取り込まれ、内 [!DNL Sensor] の測定データとして使用できるようになりま [!DNL Site]す。

次に、セッションcookieを使用して、訪問者が入力した単一のフォーム変数を取り込む例を示します。

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

この例では、関数が呼び出されて、訪問者のコンピューター上にフィールドの名前と、フォームフィールドに入力された値を使用してセッションcookieが設定されます。 フォームが送信され、後続のWebページがリクエストされると、セッションcookieのセットがWebサーバーに渡され、によって収集されま [!DNL Sensor]す。 したがって、次のデータは、Data Workbenchサーバー内でデータ分析に使用できます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | v_1 cookieに関連付けられている値。 この値は、セッションcookieが設定されるフォームフィールドに入力されたNAMEを表します。 | v_1=John Smith |

セッションcookieは、HTMLページ内に存在するフォームフィールドや埋め込みJavaScript変数を繰り返し取り込むためにも利用できます。 次の例では、JavaScriptを使用して、HTMLファイル内に存在するフォームフィールドを再帰的に取り込み、適切なname=valueのペアを持つセッションcookieを設定します。

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

この例では、訪問者のコンピューター上に、フォーム内に存在するすべてのフォームフィールドの名前と値を使用してセッションcookieが設定されます。 これには、入力フィールド、チェックボックス、ラジオボタン、選択ボックス、テキスト領域が含まれます。 この例に示すように、フォームフィールドの数が不明なので、すべてのフォーム名とフィールドの値をアンパサンドで区切った1つの文字列として取り込む必要があります。 この手順は、ユーザーがコンピューター上で一度に持つCookieの数が制限されているので、実行する必要があります。 Microsoft Internet Explorerでは、最も古いCookieの削除を開始する前に、20個のセッションCookieのみを表示できます。
