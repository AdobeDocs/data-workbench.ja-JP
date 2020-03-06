---
description: クエリ文字列変数をJavaScriptリクエストに追加して、リクエストが行われたときに追加の測定値を収集できます。
solution: Analytics
title: 追加情報の取得
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 追加情報の取得{#acquiring-additional-information}

クエリ文字列変数をJavaScriptリクエストに追加して、リクエストが行われたときに追加の測定値を収集できます。

これらの変数は、手動で追加するか、ページ自体のスクリプトで追加できます。

次のコードを例として使用し、ページから取得できる追加情報をスクリプトを使用して埋め込みオブジェクトに追加できます。

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

この例では、v_1およびv_2のスクリプト変数は、Webページ内の別の関数から派生させることができます。 変数が例として挿入されています。 各リクエストで取得したベースライン測定に加え、上記のURLのリクエストを使用して、次の拡張測定が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pnクエリ文字列変数に関連付けられた値 | v_pn=申込フォーム |
| v_1= | v_1クエリ文字列変数に関連付けられた値 | v_1=99.99 |
| v_2= | v_2クエリ文字列変数に関連付けられた値 | v_2=visa |

