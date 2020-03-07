---
description: リファレンスページタグを使用してリンククリックの収集を容易にする手順です。
solution: Analytics
title: リンククリックの追跡
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# リンククリックの追跡{#tracking-link-clicks}

リファレンスページタグを使用してリンククリックの収集を容易にする手順です。

の導入により、訪問者が [!DNL Reference Page Tag]特定のページを訪問する際にクリックしたリンク（またはhref値）を示す測定データを収集できます。 通常、このコレクションには、HTMLページへの追加のリンク識別子の実装は含まれません。

を使用してリンククリック数を収集しやすくするに [!DNL Reference Page Tag]は、次の手順を実行します。

1. 次のコードを、という名前の既存のファイルにコピーしま [!DNL zig.js]す。

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Webサーバー上のディレクトリに、1ピクセルx 1ピクセルの画像ファイルを [!DNL zag2.gif] 作成するか、このファイルを配置します。
1. 変数を変更 [!DNL lc.src] して、ファイルの参照元のWebサイトの適切なドメインを [!DNL zag2.gif]参照するようにします。

1. およびファイルに対して適切なキャッシュ制御ヘッダーが確立されてい [!DNL zag.gif] ることを確 [!DNL zig.js] 認します。

1. リンククリック値の収集元のHTMLファイル内で、ページのリンククリックを取 [!DNL Reference Page Tag Execution Call] り込むようにを変更 [!DNL Page Tag Execution Script] する必要があります。 これを行うには、次のコード例で強調表示されているように、vlc変数の値を「1」に変更します。

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_ln= | インプレッションキャンペーンを示す値 | v_ln=&quot;About%20Us&quot; |

