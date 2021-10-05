---
description: サードパーティの Web サイトリンク間のアクティビティをキャプチャして、出口ターゲットの分析を有効にします。
title: 外部リンクへの離脱数の追跡
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# 外部リンクへの離脱数の追跡{#tracking-exits-to-external-links}

サードパーティの Web サイトリンク間のアクティビティをキャプチャして、出口ターゲットの分析を有効にします。

Web ページには、サードパーティの Web サイトへのリンクを含めることができ、それらのリンク間のアクティビティを取り込んで、出口ターゲットの分析を有効にできます。特に、サードパーティのサイトが紹介料を支払う場合です。 クリックイベントはデフォルトでサードパーティシステムのログファイルに書き込まれるので、クリックイベントをローカルにキャプチャするには、リンクに対して変更を加える必要があります。 Web サイト内に存在するサードパーティリンクは、次のように変更する必要があります。

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

参照する [!DNL PageExit.htm] ファイルを作成し、次のスクリプトを含むように構造化する必要があります。

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

[!DNL PageExit.htm] ファイルに対して要求を行うと、v_eurl 値が分析目的で収集されます。 さらに、[!DNL PageExit.htm] がロードされると、指定された v_eurl のターゲットの場所に直ちにリダイレクトされます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_eurl | v_eurl クエリー文字列変数に関連付けられた値。 この値は、HTMLページ内に存在するリンクのターゲット URL を表します。 | v_eurl=www.othersite.com |
