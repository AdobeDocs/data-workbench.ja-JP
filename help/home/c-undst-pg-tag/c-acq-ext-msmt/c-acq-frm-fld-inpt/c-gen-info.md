---
description: Webページでフォームに入力した値は、JavaScriptを使用して収集し、後で（フォーム送信時に）要求されるページのクエリ文字列に追加できます。
solution: Analytics
title: 一般情報
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 一般情報{#general-information}

Webページでフォームに入力した値は、JavaScriptを使用して収集し、後で（フォーム送信時に）要求されるページのクエリ文字列に追加できます。

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

次の例では、FORM Action値で示される後続の「thankyou.asp」ページに、ブラウザーユーザーがフォームに入力した値を次のように追加します。

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

このリクエストでは、によって収集されたベースライン測定に加えて、次の拡張測定が取得されま [!DNL Sensor]す。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | NAMEフォームフィールドに関連付けられた値 | v_1=John Smith |
| v_2 | CITYフォームフィールドに関連付けられた値 | v_2=ロサンゼルス |
| v_3 | STATEフォームフィールドに関連付けられた値 | v_3=カリフォルニア |
| v_4 | 「ZIPフォーム」フィールドに関連付けられた値 | v_4=90210 |

