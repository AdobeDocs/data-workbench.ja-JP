---
description: サードパーティの Web サイトリンクをまたいでアクティビティをキャプチャし、出口ターゲットの分析を有効にします。
title: 外部リンクへの離脱数の追跡
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# 外部リンクへの離脱数の追跡{#tracking-exits-to-external-links}

{{eol}}

サードパーティの Web サイトリンクをまたいでアクティビティをキャプチャし、出口ターゲットの分析を有効にします。

Web ページには、サードパーティの Web サイトへのリンクを含めることができます。また、これらのリンクをまたいだアクティビティを取り込んで、出口ターゲット分析を有効にすることができます。特に、サードパーティのサイトが紹介料の支払いを担当する場合。 クリックイベントはデフォルトでサードパーティシステムのログファイルに書き込まれるので、クリックイベントをローカルにキャプチャするには、リンクに変更を加える必要があります。 Web サイト内に存在するサードパーティリンクは、次のように変更する必要があります。

```
<A HREF=”https://www.myserver.com/PageExit.htm?v_eurl=https://www.othersite.com”>
```

参照先 [!DNL PageExit.htm] ファイルを作成し、次のスクリプトを含むように構造化する必要があります。

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

をリクエストする [!DNL PageExit.htm] ファイルに含まれている場合、v_eurl 値は分析目的で収集されます。 また、 [!DNL PageExit.htm] が読み込まれると、指定された v_eurl ターゲットの場所に直ちにリダイレクトされます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_eurl | v_eurl クエリー文字列変数に関連付けられた値。 この値は、HTMLページ内に存在するリンクのターゲット URL を表します。 | v_eurl=www.othersite.com |
