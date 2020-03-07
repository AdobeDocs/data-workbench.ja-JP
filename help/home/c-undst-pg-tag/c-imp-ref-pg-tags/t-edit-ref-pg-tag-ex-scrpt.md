---
description: 参照ページタグは、Webサーバー上に存在するページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。
solution: Analytics
title: 参照ページのタグ実行スクリプトの編集
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 参照ページのタグ実行スクリプトの編集{#editing-the-reference-page-tag-execution-script}

参照ページタグは、Webサーバー上に存在するページタグ実行スクリプトで構成され、呼び出されると、サイト訪問者が要求したページのクライアント側のすべてのデータが収集されます。

アドビのコンサルティングサ [!DNL Reference Page Tag Execution Script] ービスチームとの会議で要件を収集する際に特定される可能性のある追加情報を収集するように、を変更できます。 は、Webペ [!DNL Reference Page Tag Execution Script] ージに大量のダウンロードが追加されないように、サイズが比較的小さくなっています。

次のコー [!DNL Reference Page Tag Execution Script] ドが、という名前のファイルで提供されま [!DNL zig.js]す。

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

を使用したデータ収集を容易にするには、次 [!DNL Reference Page Tag]の手順を実行してください。

1. Webサーバー上のディレクトリに、1ピクセルx 1ピクセルの画像ファイルを [!DNL zag.gif] 作成するか、このファイルを配置します。
1. cd変数を変更して、Webサイトの適切なドメインまたはファイルの参照元のアドビの管理サービスドメインを [!DNL zag.gif] 参照します。 ファイルへの参照は、ファイル関数の実行によって作成 [!DNL zig.js] されます。 次に例を示します。

   ```
   //www.mysite.com
   ```

1. cu変数を変更して、ファイルの場所への適切なパスを参照し [!DNL zag.gif] ます。 例えば、

   ```
   /scripts
   ```

1. およびファイルに対して適切なキャッシュ制御ヘッダーが確立されてい [!DNL zag.gif] ることを確 [!DNL zig.js] 認します。