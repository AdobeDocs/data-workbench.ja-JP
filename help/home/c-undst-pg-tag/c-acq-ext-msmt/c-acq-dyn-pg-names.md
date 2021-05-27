---
description: 一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をセンサーが取得し、レポートや分析に使用できるようにする必要があります。
title: 動的ページ名の取得
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 動的ページ名の取得{#acquiring-dynamic-page-names}

一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をセンサーが取得し、レポートや分析に使用できるようにする必要があります。

これは、Webサーバーで見られるページのURLが、ブラウザーに表示されるページコンテンツを示していない場合に必要になる場合があります。 この場合、多くの場合、パーソナライゼーションまたは動的コンテンツ管理システムを使用し、ページで提供される実際のコンテンツを、URL、Cookie、関連データおよびアプリケーションロジックによってオンザフライで決定することが原因です。

埋め込みオブジェクトを実装して追加の測定を収集する場合、サイト全体のパフォーマンスに与える影響は最小限に抑える必要があります。 Adobeでは、拡張属性の収集に使用するオブジェクトとしてJavaScriptファイルを埋め込むことをお勧めします。 （JavaScriptファイルは、埋め込み画像を使用することで、Webページのレイアウトや表示に影響を与える可能性がなく、埋め込むことができます）。 埋め込みオブジェクト内で渡された情報を正確に取り込むために、Adobeは、共通名を使用することを示唆している。 命名のため、Adobeはこのオブジェクトを[!DNL zig.js]と呼びます。 [!DNL zig.js]ファイルは、[!DNL Sensor]がインストールされているWebサーバー上の適切なディレクトリ内に作成する必要があります。 リクエストが404エラーコードを返さないように、このファイルが存在する必要があります。 ファイル自体の内容は重要ではありません。 [!DNL zig.js]という名前の空のファイルを使用して、要求によって発生するネットワークトラフィックの量を最小限に抑える必要があります。

[!DNL Sensor]で、実際に提供されたページの使用可能な名前を収集するには、追跡する動的ページまたは一意のページ名を追加する動的ページに、JavaScriptコードを数行追加する必要があります。 このコードは、ページにJavaScriptのスニペットを埋め込みます。これにより、ページの読み込み中に、3番目の埋め込みオブジェクト要求がWebサーバーに対しておこなわれます。 このリクエストは、Webサーバーに返された特定のページに関する詳細を送信します。 実際に提供されたページの名前は、埋め込みオブジェクト（この場合はJavaScript）リクエストのクエリ文字列の変数としてWebサーバーに戻されます。

一般に、このようなHTMLページのそれぞれに埋め込まれるオブジェクトリクエストは、次のようになります。

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] では、JavaScriptや [!DNL Sensor] イメージのリクエストを保存する前に除外するなど、コンテンツタイプのフィルタリングルールに関係なく、リクエストが記録されま [!DNL Sensor] す。宣言されたv_pn変数は、提供される実際のページコンテンツの名前を識別し、 [!DNL Site]は、訪問者が実際に閲覧したページの名前を認識します。 v_pn値は、手動で確立することも、他のスクリプトやアプリケーションコードで確立することもできます。

値が収集されたら、 [!DNL zag.gif] URI（例えば[!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]）に追加されたクエリー文字列変数（name=valueペア、例えば）の内容を[!DNL zag.gif] URIの拡張として使用するように、Data Workbenchサーバーを設定できます。 HTTP要求ごとに取得されるベースライン測定に加え、この要求を用いて拡張測定を取得する。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pnクエリー文字列変数に関連付けられた値 | v_pn=Application Form |
