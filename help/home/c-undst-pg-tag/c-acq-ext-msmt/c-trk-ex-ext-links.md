---
description: サードパーティのWebサイトリンク間のアクティビティをキャプチャして、出口ターゲットの分析を有効にします。
title: 外部リンクへの離脱数の追跡
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# 外部リンクへの離脱数の追跡{#tracking-exits-to-external-links}

サードパーティのWebサイトリンク間のアクティビティをキャプチャして、出口ターゲットの分析を有効にします。

WebページにはサードパーティのWebサイトへのリンクを含めることができ、それらのリンク間のアクティビティを取り込んで、出口ターゲットの分析を有効にできます。特に、サードパーティのサイトが紹介料を支払う場合に役立ちます。 クリックイベントはデフォルトでサードパーティシステムのログファイルに書き込まれるので、クリックイベントをローカルにキャプチャするには、リンクに変更を加える必要があります。 Webサイト内に存在するサードパーティリンクは、次のように変更する必要があります。

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

参照する[!DNL PageExit.htm]ファイルを作成し、次のスクリプトを含むように構造化する必要があります。

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

[!DNL PageExit.htm]ファイルに対して要求を行うと、v_eurl値が分析目的で収集されます。 さらに、[!DNL PageExit.htm]が読み込まれると、指定されたv_eurlターゲットの場所に直ちにリダイレクトされます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_eurl | v_eurlクエリー文字列変数に関連付けられた値。 この値は、HTMLページ内に存在するリンクのターゲットURLを表します。 | v_eurl=www.othersite.com |
