---
description: 一部のサイトでは、埋め込みオブジェクトリクエストを使用して情報を Web サーバーに渡し、実際に提供されたページに関する詳細を Sensor が取得し、レポートや分析に使用できるようにする必要があります。
title: 動的ページ名の取得
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 動的ページ名の取得{#acquiring-dynamic-page-names}

{{eol}}

一部のサイトでは、埋め込みオブジェクトリクエストを使用して情報を Web サーバーに渡し、実際に提供されたページに関する詳細を Sensor が取得し、レポートや分析に使用できるようにする必要があります。

これは、Web サーバーで見られるページの URL が、ブラウザーに表示されるページコンテンツを示していない場合に必要になる場合があります。 このケースは、多くの場合、パーソナライゼーションまたは動的コンテンツ管理システムを使用した結果として生じます。このシステムでは、ページで提供される実際のコンテンツが、URL、Cookie、関連データおよびアプリケーションロジックによってその場で決定されます。

追加の測定値を収集するために埋め込みオブジェクトを実装する場合、サイト全体のパフォーマンスに与える影響は最小限に抑えられます。 Adobeでは、拡張属性の収集に使用するオブジェクトとして JavaScript ファイルを埋め込むことをお勧めします。 （JavaScript ファイルは、埋め込み画像を使用することで、Web ページのレイアウトや表示に影響を与える可能性がなく、埋め込むことができます）。 埋め込みオブジェクト内で渡された情報を正確に取り込むために、Adobeは、共通名を使用することを示唆しています。 命名の目的で、Adobeはこのオブジェクトを [!DNL zig.js]. この [!DNL zig.js] ファイルは、 [!DNL Sensor] がインストールされている。 このファイルは、リクエストが 404 エラーコードを返さないように、存在する必要があります。 ファイル自体の内容は重要ではありません。 という名前の空のファイルを使用する必要があります。 [!DNL zig.js] リクエストの結果発生するネットワークトラフィックの量を最小限に抑える。

の場合 [!DNL Sensor] 実際に提供されたページの使用可能な名前を収集するには、追跡する動的ページまたは一意のページ名を追加するページに、いくつかの JavaScript コードを追加する必要があります。 このコードは、ページに JavaScript のスニペットを埋め込みます。これにより、ページの読み込み中に Web サーバーに 3 番目の埋め込みオブジェクト要求が送信されます。 このリクエストは、Web サーバーに返された特定のページに関する詳細を送信します。 実際に提供されたページの名前は、埋め込みオブジェクト（この場合は JavaScript）リクエストのクエリ文字列内の変数として Web サーバーに返されます。

一般に、このような各HTMLページに埋め込まれるオブジェクトリクエストは、次のようになります。

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] 確実に [!DNL Sensor] にもかかわらず、リクエストを記録します。 [!DNL Sensor] コンテンツタイプのフィルタリングルールを使用します。例えば、JavaScript やイメージリクエストを保存する前にフィルタリングして除外するなどです。 宣言済みの v_pn 変数は、提供される実際のページコンテンツの名前を識別し、 [!DNL Site] は、訪問者が実際に閲覧したページの名前を把握します。 v_pn 値は、手動で確立することも、他のスクリプトやアプリケーションコードで確立することもできます。

値が収集されたら、クエリ文字列変数（name=value ペア、例えば v_pn=Application Form など）の内容を [!DNL zag.gif] URI( 例： [!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form])、を拡張した [!DNL zag.gif] URI。 HTTP リクエストごとに取得されるベースライン測定に加えて、このリクエストで拡張測定が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pn クエリー文字列変数に関連付けられた値 | v_pn=Application Form |
