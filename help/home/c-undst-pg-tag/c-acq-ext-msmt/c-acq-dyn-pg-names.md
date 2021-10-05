---
description: 一部のサイトでは、埋め込まれたオブジェクトリクエストを使用して Web サーバーに情報を渡し、実際に提供されたページの詳細を Sensor が取得し、レポートや分析に使用できるようにする必要があります。
title: 動的ページ名の取得
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 動的ページ名の取得{#acquiring-dynamic-page-names}

一部のサイトでは、埋め込まれたオブジェクトリクエストを使用して Web サーバーに情報を渡し、実際に提供されたページの詳細を Sensor が取得し、レポートや分析に使用できるようにする必要があります。

これは、Web サーバーで見られるページの URL が、ブラウザーに表示されるページコンテンツを示していない場合に必要になる場合があります。 多くの場合、パーソナライゼーションまたは動的コンテンツ管理システムを使用して、ページで提供される実際のコンテンツを、URL、Cookie、関連データおよびアプリケーションロジックによってその場で決定する結果です。

埋め込みオブジェクトを実装してさらに測定を収集する場合、サイト全体のパフォーマンスに与える影響は最小限に抑える必要があります。 Adobeから、拡張属性の収集に使用するオブジェクトとして JavaScript ファイルを埋め込むことをお勧めします。 （JavaScript ファイルは、埋め込み画像を使用することで、Web ページのレイアウトや表示に影響を与える可能性がなく、埋め込むことができます）。 埋め込みオブジェクト内で渡された情報を正確に取り込むために、Adobeは、共通名を使用することを示唆している。 命名の目的で、Adobeはこのオブジェクトを [!DNL zig.js] と呼びます。 [!DNL zig.js] ファイルは、[!DNL Sensor] がインストールされている Web サーバー上の適切なディレクトリ内に作成する必要があります。 このファイルは、リクエストが 404 エラーコードを返さないように存在する必要があります。 ファイル自体の内容は重要ではありません。 [!DNL zig.js] という名前の空のファイルを使用して、要求の結果発生するネットワークトラフィックの量を最小限に抑える必要があります。

[!DNL Sensor] が実際に提供されたページの使用可能な名前を収集するには、追跡する動的ページまたは一意のページ名を追加する動的ページに、JavaScript コードを数行追加する必要があります。 このコードは、ページに JavaScript のスニペットを埋め込みます。これにより、ページの読み込み中に、3 番目の埋め込みオブジェクト要求が Web サーバーに送信されます。 このリクエストは、Web サーバーに返された特定のページに関する詳細を送信します。 実際に提供されたページの名前は、埋め込みオブジェクト（この場合は JavaScript）リクエストのクエリ文字列内の変数として Web サーバーに返されます。

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

[!DNL Log=1] は、JavaScript や [!DNL Sensor] イメージリクエストを保存する前にフィルタリングするなど、コンテンツタイプのフィルタリングルールに [!DNL Sensor] 反して、リクエストをログに記録します。宣言された v_pn 変数は、実際に提供されるページコンテンツの名前を識別し、 [!DNL Site] は、訪問者が実際に閲覧したページの名前を把握できます。 v_pn 値は、手動で、または他のスクリプトやアプリケーションコードで確立できます。

値を収集した後、 [!DNL zag.gif] URI（例えば [!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]）に追加されたクエリー文字列変数（name=value ペア、v_pn=Application Form）の内容を [!DNL zag.gif] URI の拡張として使用するように、Data Workbench サーバーを設定できます。 HTTP リクエストごとに取得されるベースライン測定に加えて、このリクエストで拡張測定が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pn クエリー文字列変数に関連付けられた値 | v_pn=Application Form |
