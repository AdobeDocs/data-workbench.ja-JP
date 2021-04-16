---
description: 一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をSensorが取得し、レポートや分析に使用できるようにする必要があります。
title: 動的ページ名の取得
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 動的ページ名の取得{#acquiring-dynamic-page-names}

一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をSensorが取得し、レポートや分析に使用できるようにする必要があります。

これは、Webサーバーで見られるページのURLが、ブラウザーに表示されるページコンテンツを示していない場合に必要になる場合があります。 この場合、多くの場合、ページで提供される実際のコンテンツがURL、Cookie、関連データおよびアプリケーションロジックによってその場で決定される、パーソナライゼーションまたは動的コンテンツ管理システムの使用が原因です。

追加の測定値を収集するために埋め込みオブジェクトを実装する場合、サイト全体のパフォーマンスに最小限の影響を与える必要があります。 拡張属性の収集に使用するオブジェクトとしてJavaScriptファイルを埋め込むことをお勧めします。 （埋め込み画像を使用すると、Webページのレイアウトや表示に影響を与えることなく、JavaScriptファイルを埋め込むことができます）。 埋め込みオブジェクト内で渡された情報を正確に取り込むために、Adobeからも共通名の使用が示唆されます。 命名の目的で、Adobeはこのオブジェクトを[!DNL zig.js]と呼びます。 [!DNL zig.js]ファイルは、[!DNL Sensor]がインストールされているWebサーバー上の適切なディレクトリ内に作成する必要があります。 このファイルは、要求が404エラーコードを返さないように存在する必要があります。 ファイル自体の内容は重要ではありません。 [!DNL zig.js]という名前の空のファイルを使用して、要求の結果発生するネットワークトラフィックの量を最小限に抑える必要があります。

[!DNL Sensor]が実際に提供されたページの使用可能な名前を収集するには、追跡する動的ページ、または一意のページ名を追加したい動的ページに、JavaScriptコードを数行追加する必要があります。 次のコードは、ページにJavaScriptのスニペットを埋め込みます。これにより、ページの読み込み中に、3番目の埋め込みオブジェクトのリクエストがWebサーバーに対して行われます。 この要求は、Webサーバーに返された特定のページに関する詳細を送信します。 実際に提供されたページの名前は、埋め込みオブジェクト（この場合はJavaScript）リクエストのクエリ文字列内の変数としてWebサーバーに返されます。

一般に、このようなHTMLページに埋め込まれるオブジェクトリクエストは、次のようになります。

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

[!DNL Log=1] では、 [!DNL Sensor] コンテンツタイプのフィルタリングルールに反して、JavaScriptやイメージ要求を保存する前にフィルタリングするなどの反対の処理ルールを適用して、要求を [!DNL Sensor] ログに記録します。v_pn変数は、訪問者が実際に閲覧したページの名前を[!DNL Site]に知らせるために、提供される実際のページコンテンツの名前を識別します。 v_pn値は、手動または他のスクリプトやアプリケーションコードで設定できます。

値を収集した後、[!DNL zag.gif] URI（例えば[!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]）に付加されたクエリ文字列変数（name=valueペア、v_pn=Application Form）の内容を[!DNL zag.gif] URIの補強として使用するように、Data Workbenchサーバーを設定できます。 HTTPリクエストのたびに取得されるベースライン測定に加えて、このリクエストを使用して拡張測定が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pnクエリ文字列変数に関連付けられた値 | v_pn=Application Form |
