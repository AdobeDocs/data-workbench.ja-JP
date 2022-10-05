---
description: 参照ページタグは、Web サーバー上にあるページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者がリクエストしたページのすべてのクライアント側データが収集されます。
title: 参照ページタグ実行スクリプトの編集
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 6%

---

# 参照ページタグ実行スクリプトの編集{#editing-the-reference-page-tag-execution-script}

{{eol}}

参照ページタグは、Web サーバー上にあるページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者がリクエストしたページのすべてのクライアント側データが収集されます。

次の項目を変更できます。 [!DNL Reference Page Tag Execution Script] Adobeコンサルティングサービスチームとの要件収集会議で特定できる追加情報を収集する。 この [!DNL Reference Page Tag Execution Script] はサイズが比較的小さいので、web ページへの大きなダウンロードの追加を避けます。

以下 [!DNL Reference Page Tag Execution Script] コードが [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

を使用したデータ収集を容易にする [!DNL Reference Page Tag]、次の手順を実行します。

1. という名前の 1 ピクセル x 1 ピクセルの画像ファイルを作成または配置します。 [!DNL zag.gif] を web サーバー上のディレクトリに追加します。
1. cd 変数を変更して、Web サイトまたはAdobe管理サービスドメインの適切なドメインを参照します。 [!DNL zag.gif] ファイルが参照されています。 ファイルへの参照は、 [!DNL zig.js] ファイル関数 次に例を示します。

   ```
   //www.mysite.com
   ```

1. cu 変数を変更して、 [!DNL zag.gif] ファイル。 例：

   ```
   /scripts
   ```

1. 適切なキャッシュ制御ヘッダーが [!DNL zag.gif] および [!DNL zig.js] ファイル。
