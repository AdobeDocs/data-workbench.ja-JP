---
description: Sensorは、収集されたBaseline Measurementデータの一部として、Webサーバーからリクエストを行う際に、訪問者のコンピューターから送信されたドメインcookieを収集します。
title: cookie を使用した測定データの取得
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# cookie を使用した測定データの取得{#acquiring-measurement-data-through-cookies}

Sensorは、収集されたBaseline Measurementデータの一部として、Webサーバーからリクエストを行う際に、訪問者のコンピューターから送信されたドメインcookieを収集します。

これには、訪問者がシステムとやり取りしたときにWebサイトで設定される永続的なcookieとセッションcookieの両方が含まれます。

ほとんどの場合、Webサイトは永続的なcookieを設定して訪問者を識別したり、以降の訪問者セッション内で使用するためのユーザー入力を取り込んだりします。 永続的なcookieに書き込まれ、保存される情報は、Data Workbenchサーバー内の他のすべての測定データと共に取得して使用できます。

このような永続的なcookieの例としては、訪問者のマシンに存在するドメイン固有のcookieに存在する数値キーの形で顧客識別子を関連付けることができます。 ユーザーをリターン訪問者として特定するだけでなく、永続的なcookieを使用して訪問者を再訪問者としてさらに識別したり、訪問者を顧客データベース内の情報に結び付けて、オフライン顧客人口統計情報を[!DNL Site]内に表示し、インタラクティブ分析に使用したりできます。

セッションcookieは、Webサイト内のフォームフィールドやその他の動的なインタラクティブ要素からユーザー入力を収集するのに適したメカニズムです。 ユーザー固有の入力データを取り込むためのフォームを実装するWebサイトの場合、セッションがアクティブである限り、セッションcookieに情報が残ります。 ユーザーがWebサイトを離れたり、セッションが終了したりした場合、その情報はユーザーのコンピューターに保存されなくなります。 ただし、入力された情報は[!DNL Sensor]によって取り込まれ、[!DNL Site]内で測定データとして使用できるようになります。

次に、セッションcookieを使用して、訪問者が入力した1つのフォーム変数を取り込む例を示します。

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

この例では、関数が呼び出されて、訪問者のマシン上に、フィールド名とフォームフィールドに入力された値を持つセッションcookieが設定されます。 フォームが送信され、後続のWebページがリクエストされると、セッションcookieの設定がWebサーバーに渡され、[!DNL Sensor]によって収集されます。 したがって、次のデータは、data workbenchサーバー内でdata分析で使用できます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | v_1 cookieに関連付けられている値。 この値は、セッションcookieが設定される結果となったフォームフィールドに入力されたNAMEを表します。 | v_1=John Smith |

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

この例では、訪問者のマシン上に、フォーム内に存在するすべてのフォームフィールドの名前と値を持つセッションCookieが設定されます。 入力フィールド、チェックボックス、ラジオボタン、選択ボックス、テキスト領域などがあります。 この例に示すように、フォームフィールドの数が不明なので、すべてのフォーム名とフィールドの値はアンパサンドで区切った1つの文字列として取り込む必要があります。 この手順は、ユーザーが1回のコンピューター上で持つことのできるCookieの数が制限されているので、実行する必要があります。 Microsoft Internet Explorerでは、最も古いCookieの削除が開始される前に、20個のセッションCookieしか存在しないようにします。
