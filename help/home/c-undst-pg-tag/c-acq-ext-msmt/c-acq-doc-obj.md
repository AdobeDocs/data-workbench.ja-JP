---
description: JavaScriptドキュメントオブジェクトモデルを使用すると、zig.jsファイルの要求を拡張するために追加のスクリプティングメソッドを使用できます。
title: ドキュメントオブジェクトの取得
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# ドキュメントオブジェクトの取得{#acquiring-document-objects}

JavaScriptドキュメントオブジェクトモデルを使用すると、zig.jsファイルの要求を拡張するために追加のスクリプティングメソッドを使用できます。

METAタグの値、DIVタグのID値などの情報は、名前で参照し、分析で使用する変数として収集できます。 例えば、HTMLドキュメントのMETA要素に含まれる情報を動的に取り込むには、次のJavaScript構文を使用できます。

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1= | METAVALUEクエリ文字列変数に関連付けられた値。 この値は、HTMLドキュメントのMETA要素内のデータを表します。 | v_1=このページは、「ご注文ありがとうございました」ページに関連するコンテンツを提供します。 |

データが収集されたら、分析とレポートの目的でこの測定データを処理するように、Data Workbenchサーバーを設定できます。
