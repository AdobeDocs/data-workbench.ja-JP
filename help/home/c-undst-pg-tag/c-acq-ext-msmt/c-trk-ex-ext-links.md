---
description: サードパーティのWebサイトリンク間でアクティビティをキャプチャして、出口ターゲット分析を有効にします。
solution: Analytics
title: 離脱リンクの追跡
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 離脱リンクの追跡{#tracking-exits-to-external-links}

サードパーティのWebサイトリンク間でアクティビティをキャプチャして、出口ターゲット分析を有効にします。

Webページには、サードパーティのWebサイトへのリンクを含めることができ、それらのリンク間のアクティビティをキャプチャして、Exit Target分析を有効にできます。特に、サードパーティのサイトが照会を受け取った場合に照会料を支払う必要があります。 clickイベントはデフォルトでサードパーティシステムのログファイルに書き込まれるので、clickイベントをローカルにキャプチャするには、リンクに対して変更を加える必要があります。 Webサイト内に存在するサードパーティリンクは、次のように変更する必要があります。

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

参照先のファ [!DNL PageExit.htm] イルを作成し、次のスクリプトを含むように構造化する必要があります。

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

ファイルに対してリクエストを [!DNL PageExit.htm] 行うことで、v_eurl値が分析のために収集されます。 さらに、が読み込ま [!DNL PageExit.htm] れると、指定したv_eurlターゲットの場所に直ちにリダイレクトされます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_eurl | v_eurlクエリ文字列変数に関連付けられた値。 この値は、HTMLページ内に存在するリンクのターゲットURLを表します。 | v_eurl=www.othersite.com |

