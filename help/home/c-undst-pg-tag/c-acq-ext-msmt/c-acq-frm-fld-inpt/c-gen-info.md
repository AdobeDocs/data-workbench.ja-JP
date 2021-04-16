---
description: Webページ内のフォームに入力された値は、JavaScriptを使用して収集し、後に（フォーム送信時に）要求されるページのクエリ文字列に追加できます。
title: 一般情報
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# 一般情報{#general-information}

Webページ内のフォームに入力された値は、JavaScriptを使用して収集し、後に（フォーム送信時に）要求されるページのクエリ文字列に追加できます。

これは次の例に示します。 HTMLページで使用するフォーム検証スクリプトの後に、このJavaScriptを含めます。

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

次の例では、ブラウザーユーザーがフォームに入力した値を、FORM Action値で示される後続の「thankyou.asp」ページに追加します。

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

[!DNL Sensor]が収集するベースライン測定に加えて、このリクエストで以下の拡張測定値が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | 「NAME」フォームフィールドに関連付けられた値 | v_1=John Smith |
| v_2 | CITYフォームフィールドに関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATEフォームフィールドに関連付けられた値 | v_3=カリフォルニア |
| v_4 | 「ZIPフォーム」フィールドに関連付けられた値 | v_4=90210 |
