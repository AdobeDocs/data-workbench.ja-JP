---
description: 参照ページタグは、Webサーバー上にあるページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。
title: 参照ページタグ実行スクリプトの編集
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 6%

---

# 参照ページタグ実行スクリプトの編集{#editing-the-reference-page-tag-execution-script}

参照ページタグは、Webサーバー上にあるページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。

[!DNL Reference Page Tag Execution Script]を変更して、Adobeコンサルティングサービスチームとの要件収集会議で特定される可能性のある追加情報を収集できます。 [!DNL Reference Page Tag Execution Script]は、Webページへの大きなダウンロードの追加を避けるために、サイズが比較的小さくなります。

次の[!DNL Reference Page Tag Execution Script]コードは、[!DNL zig.js]という名前のファイルで提供されます。

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

[!DNL Reference Page Tag]を使用したデータ収集を容易にするには、次の手順を実行します。

1. [!DNL zag.gif]という名前の1ピクセルx 1ピクセルの画像ファイルを作成するか、Webサーバー上に存在するディレクトリに配置します。
1. cd変数を変更して、Webサイトまたは[!DNL zag.gif]ファイルの参照元であるAdobe管理サービスドメインの適切なドメインを参照します。 ファイルへの参照は、[!DNL zig.js]ファイル関数の実行によって作成されます。 次に例を示します。

   ```
   //www.mysite.com
   ```

1. cu変数を変更して、[!DNL zag.gif]ファイルの場所に適したパスを参照します。 例：

   ```
   /scripts
   ```

1. [!DNL zag.gif]ファイルと[!DNL zig.js]ファイルに対して適切なキャッシュ制御ヘッダーが確立されていることを確認します。
