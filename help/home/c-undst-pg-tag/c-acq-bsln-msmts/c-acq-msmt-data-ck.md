---
description: センサーは、収集されたベースライン測定データの一部として、Web サーバーからリクエストをおこなう際に訪問者のマシンから送信されたドメイン Cookie を収集します。
title: cookie を使用した測定データの取得
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# cookie を使用した測定データの取得{#acquiring-measurement-data-through-cookies}

{{eol}}

センサーは、収集されたベースライン測定データの一部として、Web サーバーからリクエストをおこなう際に訪問者のマシンから送信されたドメイン Cookie を収集します。

これには、訪問者がシステムを操作したときに Web サイトが設定する永続的な Cookie とセッション Cookie の両方が含まれます。

ほとんどの場合、Web サイトは、訪問者を識別するために永続的な cookie を設定し、以降の訪問者セッションで使用するユーザー入力を取得します。 永続的な cookie に書き込まれ、保存される情報は、Data Workbench サーバー内の他のすべての測定データと共に取得して使用できます。

このような永続的な cookie の例としては、訪問者のマシン上に存在するドメイン固有の cookie 内に存在する数値キーの形式で顧客識別子を含めることができます。 ユーザーを再訪問者として識別するだけでなく、永続的な cookie を使用して、訪問者を再訪問者としてさらに識別したり、訪問者を顧客データベース内の情報に関連付けて、オフラインの顧客人口統計情報を [!DNL Site] インタラクティブな分析に使用されます。

セッション cookie は、Web サイト内のフォームフィールドやその他の動的インタラクティブ要素を通じてユーザー入力を収集する良いメカニズムです。 ユーザー固有の入力データを取り込むためのフォームを実装する Web サイトの場合、情報は、セッションがアクティブである限り、セッション cookie に残ります。 ユーザーが Web サイトを離れたり、セッションが終了したりすると、その情報はユーザーのコンピューターに保存されなくなります。 ただし、入力された情報は、 [!DNL Sensor] およびは内で測定データとして使用可能 [!DNL Site].

次に、訪問者が入力した単一のフォーム変数をセッション cookie を使用して取得する例を示します。

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

この例では、関数が呼び出されて、フィールド名とフォームフィールドに入力された値を使用して、訪問者のマシン上にセッション Cookie が設定されます。 フォームが送信され、後続の Web ページがリクエストされると、セッション Cookie が Web サーバーに渡され、が収集します。 [!DNL Sensor]. したがって、Data Workbench サーバー内では、次のデータをデータ分析に使用できます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | v_1 Cookie に関連付けられている値。 この値は、セッション Cookie が設定される結果としてフォームフィールドに入力された NAME を表します。 | v_1=John Smith |

また、セッション cookie を使用して、フォームフィールドや、セッションページ内に存在する多数の埋め込み JavaScript 変数を反復的に取り込むこともできます。 次の例では、JavaScript を使用して、HTMLファイル内に存在するフォームフィールドを再帰的に取り込み、適切な name=value のペアを持つセッション cookie を設定します。

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

この例では、訪問者のマシン上に、フォーム内に存在するすべてのフォームフィールドの名前と値を使用してセッション Cookie が設定されます。 入力フィールド、チェックボックス、ラジオボタン、選択ボックス、テキスト領域が含まれます。 この例のように、フォームフィールドの数が不明なので、すべてのフォーム名とフィールドの値を、アンパサンドで区切られた単一の文字列として取り込む必要があります。 この手順は、ユーザーがコンピューター上で一度に持つ Cookie の数が制限されているので、実行する必要があります。 Microsoft Internet Explorer では、20 個のセッション Cookie のみが存在し、最も古いセッション Cookie の削除が開始されます。
