---
description: JavaScript ドキュメントオブジェクトモデルを使用すると、追加のスクリプティングメソッドを使用して zig.js ファイルのリクエストを拡張できます。
title: ドキュメントオブジェクトの取得
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# ドキュメントオブジェクトの取得{#acquiring-document-objects}

JavaScript ドキュメントオブジェクトモデルを使用すると、追加のスクリプティングメソッドを使用して zig.js ファイルのリクエストを拡張できます。

META タグの値、DIV タグの ID 値などの情報を名前で参照し、分析に使用する変数として収集できます。 例えば、HTMLドキュメントの META 要素内に含まれる情報を動的に取り込むには、次の JavaScript 構文を使用できます。

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_1"] = metacontent;
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_1= | METAVALUE クエリー文字列変数に関連付けられた値。 この値は、HTML・ドキュメントの META 要素内のデータを表します。 | v_1=このページは、「ご注文ありがとうございました」ページに関連するコンテンツを提供します。 |

データの収集後、分析とレポート作成の目的で、この測定データを処理するように Data Workbench サーバーを設定できます。
