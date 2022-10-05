---
description: 参照ページタグを使用してリンククリック数の収集を容易にする手順です。
title: リンククリック数の追跡
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# リンククリック数の追跡{#tracking-link-clicks}

{{eol}}

参照ページタグを使用してリンククリック数の収集を容易にする手順です。

をデプロイする [!DNL Reference Page Tag]を使用すると、特定のページの訪問中に訪問者がクリックしたリンク（または href 値）を示す測定データを収集できます。 通常、このコレクションには、追加のリンク識別子をHTMLページに実装する必要はありません。

を使用してリンククリック数を簡単に収集できるようにする [!DNL Reference Page Tag]、次の手順を実行します。

1. 次のコードを、 [!DNL zig.js]:

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

1. という名前の 1 ピクセル x 1 ピクセルの画像ファイルを作成または配置します。 [!DNL zag2.gif] を web サーバー上のディレクトリに追加します。
1. を変更します。 [!DNL lc.src] 変数を使用して、Web サイトの適切なドメインを参照します。 [!DNL zag2.gif]ファイルが参照されています。

1. 適切なキャッシュ制御ヘッダーが [!DNL zag.gif] および [!DNL zig.js] ファイル。

1. リンクのクリック値を収集するHTMLファイル内で、 [!DNL Reference Page Tag Execution Call] 次の情報を伝えるために変更する必要があります [!DNL Page Tag Execution Script] をクリックして、そのページのリンククリック数をキャプチャします。 これをおこなうには、次のコード例で示すように、vlc 変数の値を「1」に変更します。

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE
var v = {};
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_ln= | インプレッションキャンペーンを示す値 | v_ln=&quot;About%20Us&quot; |
