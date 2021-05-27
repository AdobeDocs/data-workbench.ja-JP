---
description: Sensorは、収集されたベースライン測定データの一部として、Webサーバーからリクエストを送信する際に、訪問者のマシンから送信されたドメインCookieを収集します。
title: cookie を使用した測定データの取得
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# cookie を使用した測定データの取得{#acquiring-measurement-data-through-cookies}

Sensorは、収集されたベースライン測定データの一部として、Webサーバーからリクエストを送信する際に、訪問者のマシンから送信されたドメインCookieを収集します。

これには、訪問者がシステムを操作したときにWebサイトで設定される永続的なCookieとセッションCookieの両方が含まれます。

ほとんどの場合、Webサイトは訪問者を識別するために永続的なcookieを設定し、後続の訪問者セッションで使用するユーザー入力を取り込みます。 永続的なcookieに書き込まれ、保存される情報は、Data Workbenchサーバー内の他のすべての測定データと共に取得して使用できます。

このような永続的なcookieの例としては、訪問者のマシン上に存在するドメイン固有のcookie内に存在する数値キーの形式で顧客識別子が含まれます。 永続的なcookieは、ユーザーを再訪問者として識別するだけでなく、訪問者を再訪問者として識別したり、オフラインの顧客人口統計情報を[!DNL Site]内に表示してインタラクティブ分析に使用したりする目的にも使用できます。

セッションcookieは、Webサイト内のフォームフィールドやその他の動的インタラクティブ要素からユーザー入力を収集する良いメカニズムです。 ユーザー固有の入力データを取り込むためのフォームを実装するWebサイトの場合、セッションがアクティブである限り、情報はセッションcookieに残ります。 ユーザーがWebサイトを離れたり、セッションが終了したりすると、その情報はユーザーのコンピューターに保存されなくなります。 ただし、入力された情報は[!DNL Sensor]によって取り込まれ、[!DNL Site]内の測定データとして使用できます。

以下は、セッションcookieを使用して、訪問者が入力した単一のフォーム変数を取り込む例です。

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

この例では、関数が呼び出されて、フィールドの名前とフォームフィールドに入力された値を使用して、訪問者のマシン上にセッションCookieを設定します。 フォームが送信され、後続のWebページがリクエストされると、設定されたセッションCookieがWebサーバーに渡され、[!DNL Sensor]によって収集されます。 したがって、次のデータは、Data Workbenchサーバー内でデータ分析に使用できます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | v_1 Cookieに関連付けられている値。 この値は、セッションCookieが設定されたフォームフィールドに入力されたNAMEを表します。 | v_1=John Smith |

また、セッションcookieを使用して、HTMLページ内に存在するフォームフィールドや多数の埋め込みJavaScript変数を反復的に取り込むこともできます。 次の例では、JavaScriptを使用して、HTMLファイル内に存在するフォームフィールドを再帰的に取り込み、適切なname=valueのペアを持つセッションcookieを設定します。

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

この例では、訪問者のマシン上に、フォーム内に存在するすべてのフォームフィールドの名前と値を持つセッションCookieが設定されます。 入力フィールド、チェックボックス、ラジオボタン、選択ボックス、テキスト領域が含まれます。 この例に示すように、フォームフィールドの数が不明なので、すべてのフォーム名とフィールドの値を、アンパサンドで区切られた単一の文字列として取り込む必要があります。 この手順は、ユーザーがコンピューター上で一度に持つCookieの数が制限されているために実行する必要があります。 Microsoft Internet Explorerでは、最も古いセッションCookieを削除し始める前に、20個のセッションCookieのみが存在することを許可しています。
