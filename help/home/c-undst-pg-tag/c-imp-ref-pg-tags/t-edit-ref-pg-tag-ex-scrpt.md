---
description: 参照ページタグは、Webサーバー上に存在するページタグ実行スクリプトで構成されます。このスクリプトを呼び出すと、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。
title: 参照ページタグ実行スクリプトの編集
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 6%

---

# 参照ページタグ実行スクリプトの編集{#editing-the-reference-page-tag-execution-script}

参照ページタグは、Webサーバー上に存在するページタグ実行スクリプトで構成されます。このスクリプトを呼び出すと、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。

[!DNL Reference Page Tag Execution Script]を変更して、Adobeコンサルティングサービスチームとのミーティングで特定される可能性のある追加情報を収集できます。 [!DNL Reference Page Tag Execution Script]のサイズは比較的小さく、Webページへのダウンロード数が多くなるのを防ぎます。

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

1. [!DNL zag.gif]という名前の1ピクセルx 1ピクセルの画像ファイルを作成するか、Webサーバー上のディレクトリに配置します。
1. cd変数を変更して、[!DNL zag.gif]ファイルの参照元であるWebサイトまたはAdobe管理サービスドメインの適切なドメインを参照します。 ファイルへの参照は、[!DNL zig.js]ファイル関数の実行によって作成されます。 次に例を示します。

   ```
   //www.mysite.com
   ```

1. cu変数を変更して、[!DNL zag.gif]ファイルの場所への適切なパスを参照します。 例えば、

   ```
   /scripts
   ```

1. [!DNL zag.gif]ファイルと[!DNL zig.js]ファイルに対して、適切なキャッシュ制御ヘッダーが確立されていることを確認します。
