---
description: Flashを使用して構築されたWebサイトは、リッチメディアコンテンツ内で実行される訪問者アクションのキャプチャに関して、特別な注意を払う必要があります。
title: Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 7%

---

# Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡{#tracking-visitor-activity-within-flash-rich-media-content}

Flashを使用して構築されたWebサイトは、リッチメディアコンテンツ内で実行される訪問者アクションのキャプチャに関して、特別な注意を払う必要があります。

[!DNL Flash]ActionScriptを使用すると、既存の[!DNL Flash]ムービーに簡単な変更を加えて、ボタンのクリックやマウスの動きなど、訪問者とムービーとのすべての操作を追跡できます。

[!DNL Flash]ムービー内での訪問者アクティビティの追跡を容易にするには、次の手順に従ってください。

1. 次追加のActionScriptコードをムービーに追加します。 このコードは、追跡する[!DNL Flash]ムービー内のイベントが呼び出すことのできる関数を表します。

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. [!DNL flashtag.txt]という名前の空のファイルを作成し、Webサーバーに配置します。
1. 手順1の関数内で、\[[!DNL PATH_TO_WEB_SERVER]\]プレースホルダーを[!DNL flashtag.txt]ファイルの場所の完全修飾パスまたは相対パスに置き換えます。 次に例を示します。

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 追加次のActionScriptコードを、トラッキング対象のすべてのイベントに送信します。 次のコードは、イベントに関するデータを取り込むための関数呼び出しを表します。

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   次の例は、on(release)イベントの使用方法を示します。ただし、tag()関数は、on(press)、on(rollover)、on(rollout)、on(keypress)イベントなど、追跡する任意のイベントを通じて参照できます。

   プレースホルダー\[[!DNL PUT_PAGE_NAME_HERE]\]は、追跡するページまたはイベントの名前を表す文字列に置き換える必要があります。 \[[!DNL PUT_PAGE_NAME_HERE]\]変数は、手動または変数参照を使用して変更でき、[!DNL Flash]アプリケーション内のページまたはイベントの一意の名前を示します。 \[[!DNL PUT_PAGE_NAME_HERE]\]プレースホルダを置き換える値は、単純な名前で構成することも、完全なURIと同様の階層構造を表すように構造化することもできます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobeでは、コードの導入前に、ビジネス要件と開発タスクの調整を容易にし、追加の開発サイクルの可能性を減らすために、ページ名とイベント名の仕様書をコンパイルすることをお勧めします。

1. 必要に応じて、[!DNL Flash]ムービーのページやイベントに追加の変数を収集して関連付けることができます。 これを行うには、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]プレースホルダーをアンパサンド(&amp;)で区切ったname=valueのペアのセットに置き換えます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   変数は、手動または変数参照を使用して変更でき、収集してページやイベントに関連付ける追加の属性を示します。 該当する追加の変数が収集されない場合は、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]を削除します。

   [!DNL Flash]リッチメディアコンテンツ内での訪問者追跡の設定が完了しました。 イベントを呼び出すと、[!DNL (PAGENAME,VARIABLES)]タグ関数が呼び出され、次のファイルに対するHTTPリクエストが行われます。 この関数は、[!DNL Flash]ムービー内で定義されたとおりにトリガされる他の関数に加えて呼び出されます。

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

[!DNL Flash]タグActionScript関数から得られるHTTPリクエストは、[!DNL Flash]ムービー内の各イベントに関して次の情報を収集します。 テーブルの最後の行(W3C名cs-uri-クエリ)は、関数呼び出しで指定された追加の変数に対して収集された情報を表します。

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C名 </th> 
   <th colname="col2" class="entry"> 収集されたデータ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> 追跡識別子(一意の訪問者) </td> 
   <td colname="col3"> 訪問者の初期リクエスト時に<span class="wintitle"> Sensor </span>によってユーザーのブラウザーに配置されたcookieから読み取られた識別子 </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付 </p> <p>時間 </p> </td> 
   <td colname="col2"> タイムスタンプ </td> 
   <td colname="col3"> リクエストがサーバーによって処理された時刻（精度100ナノ秒）精度はサーバの環境とNTPに依存) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> コンテンツタイプ </td> 
   <td colname="col3"> サーバーから返されるオブジェクトのタイプ </td> 
   <td colname="col4"> Text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP応答ステータスコード </td> 
   <td colname="col3"> HTTPサーバーの応答のステータスを示す、サーバーによって生成される数値コード </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URIステム </td> 
   <td colname="col3"> クライアントが要求したURIのステム部分 </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> クライアントIP </td> 
   <td colname="col3"> 要求元クライアントのIPアドレス </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> サーバードメイン名 </td> 
   <td colname="col3"> 要求を処理するWebサーバーのドメイン名 </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 参照 URL </td> 
   <td colname="col3"> クライアントから送信されるHTTP転送者フィールドの内容 </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> ユーザーエージェント </td> 
   <td colname="col3"> HTTPサーバーにリクエストを行うために使用するデバイス </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0;+Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> ドメインからのクライアントcookie </td> 
   <td colname="col3"> サイトに対するすべてのユーザーのCookieの内容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> クエリー文字列 </td> 
   <td colname="col3"> クライアントが要求したURIのクエリ文字列部分（存在する場合） </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
