---
description: JavaScriptドキュメントオブジェクトモデルを使用すると、zig.jsファイルの要求を拡張する追加のスクリプティングメソッドを使用できます。
solution: Analytics
title: ドキュメントオブジェクトの取得
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ドキュメントオブジェクトの取得{#acquiring-document-objects}

JavaScriptドキュメントオブジェクトモデルを使用すると、zig.jsファイルの要求を拡張する追加のスクリプティングメソッドを使用できます。

METAタグの値、DIVタグのID値などの情報は、名前で参照し、分析に使用する変数として収集できます。 例えば、HTMLドキュメントのMETA要素に含まれる情報を動的に取り込むには、次のJavaScript構文を使用します。

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

データの収集後、Data Workbenchサーバーを設定して、分析とレポートの目的でこの測定データを処理できます。
