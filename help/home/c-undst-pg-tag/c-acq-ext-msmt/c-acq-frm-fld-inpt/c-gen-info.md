---
description: Web ページでフォームに入力された値は、JavaScript を使用して収集し、その後リクエストされるページのクエリ文字列（フォーム送信時）に追加できます。
title: 一般情報
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# 一般情報{#general-information}

{{eol}}

Web ページでフォームに入力された値は、JavaScript を使用して収集し、その後リクエストされるページのクエリ文字列（フォーム送信時）に追加できます。

これは次の例で示されています。 この JavaScript は、HTMLページで使用されるフォーム検証スクリプトの後に含めます。

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

次の使用例は、ブラウザーユーザーがフォームに入力した値を、FORM の Action 値で次のように示す後続の「thankyou.asp」ページに追加します。

```
https://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

次の拡張測定は、 [!DNL Sensor]:

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1 | 「名前」フォームフィールドに関連付けられた値 | v_1=John Smith |
| v_2 | CITY フォームフィールドに関連付けられた値 | v_2=ロサンゼルス |
| v_3 | 「状態」フォームフィールドに関連付けられている値 | v_3=カリフォルニア |
| v_4 | 「ZIP フォーム」フィールドに関連付けられた値 | v_4=90210 |
