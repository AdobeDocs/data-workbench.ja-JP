---
description: クエリー文字列変数をJavaScriptリクエストに追加して、リクエスト時に追加の測定値を収集できます。
title: 追加情報の取得
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
exl-id: ad4f5e08-b7b7-4de3-b0c2-71440facb2d1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# 追加情報の取得{#acquiring-additional-information}

クエリー文字列変数をJavaScriptリクエストに追加して、リクエスト時に追加の測定値を収集できます。

これらの変数は、手動で、またはページ自体にスクリプトを使用して追加できます。

例えば、次のコードを使用して、ページから取得できる追加情報をスクリプトを使用して埋め込みオブジェクトに追加できます。

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

この例では、v_1およびv_2のスクリプト変数をWebページ内の別の関数から導き出すことができます。 変数が例として挿入されています。 各要求で取得されるベースライン測定に加えて、上記のURLの要求を用いて、以下の拡張測定を取得する。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pnクエリー文字列変数に関連付けられた値 | v_pn=Application Form |
| v_1= | v_1クエリー文字列変数に関連付けられた値 | v_1=99.99 |
| v_2= | v_2クエリー文字列変数に関連付けられた値 | v_2=visa |
