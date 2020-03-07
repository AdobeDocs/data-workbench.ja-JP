---
description: 一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をSensorが取得し、レポートおよび分析に使用できるようにする必要があります。
solution: Analytics
title: 動的ページ名の取得
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 動的ページ名の取得{#acquiring-dynamic-page-names}

一部のサイトでは、埋め込みオブジェクトリクエストを使用してWebサーバーに情報を渡し、実際に提供されたページの詳細をSensorが取得し、レポートおよび分析に使用できるようにする必要があります。

これは、Webサーバーで見られるページのURLが、ブラウザーに表示されるページコンテンツを示していない場合に必要になる可能性があります。 この場合、多くの場合、パーソナライゼーションまたは動的コンテンツ管理システムを使用して、ページで提供される実際のコンテンツがURL、cookie、関連データおよびアプリケーションロジックによってその場で決定されます。

追加の測定値を収集するための埋め込みオブジェクトの実装は、サイト全体のパフォーマンスへの影響を最小限に抑える必要があります。 拡張属性の収集に使用するオブジェクトとしてJavaScriptファイルを埋め込むことをお勧めします。 （埋め込み画像を使用すると、Webページのレイアウトや表示に影響を及ぼすことなく、JavaScriptファイルを埋め込むことができます）。埋め込みオブジェクト内で渡された情報を正確に取り込むために、アドビでは、共通名の使用を推奨しています。 アドビでは、命名の目的でこのオブジェクトをと呼びま [!DNL zig.js]す。 ファイ [!DNL zig.js] ルは、がインストールされているWebサーバー上の適切なディレクトリ内に作成する必 [!DNL Sensor] 要があります。 要求が404エラーコードを返さないように、このファイルが存在する必要があります。 ファイル自体の内容は重要ではありません。 リクエストの結果として発生するネットワーク [!DNL zig.js] トラフィックの量を最小限に抑えるため、という名前の空のファイルを使用する必要があります。

実際 [!DNL Sensor] に提供されたページの使用可能な名前を収集するには、追跡する動的ページまたは一意のページ名を追加する動的ページに、いくつかのJavaScriptコードを追加する必要があります。 次のコードは、ページにJavaScriptのスニペットを埋め込みます。これにより、ページの読み込み中に3番目の埋め込みオブジェクトリクエストがWebサーバーに対して行われます。 このリクエストは、Webサーバーに提供された特定のページに関する詳細を送信します。 実際に提供されたページの名前は、埋め込みオブジェクト（この場合はJavaScript）リクエストのクエリ文字列内の変数としてWebサーバーに返されます。

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

[!DNL Log=1] では、JavaScript [!DNL Sensor] やイメージ要求の保存前のフィルタリングなど、コンテ [!DNL Sensor] ンツタイプのフィルタリング規則に反して、要求をログに記録します。 宣言されたv_pn変数は、実際に訪問者が閲覧したページの名前を知るために、提供さ [!DNL Site] れる実際のページコンテンツの名前を識別します。 v_pn値は、手動で、または他のスクリプトやアプリケーションコードで確立できます。

値を収集した後、 [!DNL zag.gif] URI（例えば、v_pn=Application Form）に追加されたクエリ文字列変数（name=valueペア）の内容(例えば、 [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form][!DNL zag.gif] )をURIの増強として使用するように、Data Workbenchサーバーを設定できます。 HTTPリクエストのたびに取得されるベースライン測定に加え、このリクエストを使用して拡張測定が取得されます。

| 収集されたデータ | 説明 | 例 |
|---|---|---|
| v_pn= | v_pnクエリ文字列変数に関連付けられた値 | v_pn=申込フォーム |

