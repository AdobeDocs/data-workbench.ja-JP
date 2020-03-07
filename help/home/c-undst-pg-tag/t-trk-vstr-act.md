---
description: Flashを使用して構築されたWebサイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して、特に注意が必要です。
solution: Analytics
title: Flashリッチメディアコンテンツ内の訪問者アクティビティの追跡
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Flashリッチメディアコンテンツ内の訪問者アクティビティの追跡{#tracking-visitor-activity-within-flash-rich-media-content}

Flashを使用して構築されたWebサイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して、特に注意が必要です。

ActionScriptを使用し [!DNL Flash] て、既存のムービーに簡単な変更を加え、ボタンのクリックやマウスの動きなど、訪問者がムービーとのやり取りを [!DNL Flash] すべて追跡できるようにすることができます。

ムービー内での訪問者のアクティビティ追跡を [!DNL Flash] 容易にするには、次の手順に従ってください。

1. ムービーに次のActionScriptコードを追加します。 このコードは、追跡するムービー内のイベントによって呼び出 [!DNL Flash] される関数を表します。

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. という名前の空のファイルを作成 [!DNL flashtag.txt] し、そのファイルをWebサーバーに配置します。
1. 手順1の関数内で、[!DNL [PATH_TO_WEB_SERVER]]プレースホルダーをファイルの場所の完全修飾パスまたは相対パスに置き換え [!DNL flashtag.txt] ます。 次に例を示します。

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 追跡するすべてのイベントに、次のActionScriptコードを追加します。 次のコードは、イベントに関するデータを取り込むための関数呼び出しを表します。

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   この例は、on(release)イベントの使用方法を示しています。ただし、tag()関数は、on(press)、on(rollover)、on(rollout)、on(rollout)、on(keypress)イベントなど、追跡したい任意のイベントを通じて参照できます。

   [!DNL [PUT_PAGE_NAME_HERE]]プレースホルダーは、追跡するページまたはイベントの名前を表す文字列に置き換える必要があります。 [!DNL [PUT_PAGE_NAME_HERE]]変数は、手動または変数参照を使用して変更し、アプリケーション内のページまたはイベントの一意の名前を示すことができ [!DNL Flash] ます。 [!DNL [PUT_PAGE_NAME_HERE]]プレースホルダーを置き換える値は、単純な名前で構成するか、完全なURIと同様の階層構造を表すように構造化することができます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   コードのデプロイメントの前に、ビジネス要件や開発タスクの調整を容易にし、追加の開発サイクルの可能性を減らすために、ページ名とイベント名の仕様書をコンパイルすることをお勧めします。

1. 必要に応じて、追加の変数を収集し、ムービー内のページやイベントに関連付けることがで [!DNL Flash] きます。 これを行うには、[!DNL [PUT_ADDITIONAL_VAR_HERE]]プレースホルダーをアンパサンド(&amp;)で区切ったname=valueのペアのセットに置き換えます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   変数は、手動または変数参照を使用して変更でき、収集され、ページやイベントに関連付けられる追加の属性を示します。 該当する追加の変数が収集されない場合は、[!DNL [PUT_ADDITIONAL_VAR_HERE]]を削除します。

   これで、リッチメディアコンテンツ内の訪 [!DNL Flash] 問者追跡の設定が完了しました。 イベントが呼び出されると、タグ [!DNL (PAGENAME,VARIABLES)] 関数が呼び出され、次のファイルに対するHTTPリクエストが行われます。 この関数は、ムービー内で定義されたとおりにトリガーされる他の関数に加えて、次の関数も呼び出さ [!DNL Flash] れます。

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

ActionScriptタグ関数から生成されるHTTP [!DNL Flash] リクエストは、ムービー内の各イベントに関して次の情報を収集し [!DNL Flash] ます。 表の最後の行（W3C名：cs-uri-query）は、関数呼び出しで指定された追加の変数に対して収集された情報を表します。

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
   <td colname="col2"> トラッキング識別子（個別訪問者） </td> 
   <td colname="col3"> 訪問者の最初のリクエスト時にSensorによってユーザーのブラウザーに配置さ <span class="wintitle"> れた </span> cookieから読み取られた識別子 </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付 </p> <p>時間 </p> </td> 
   <td colname="col2"> タイムスタンプ </td> 
   <td colname="col3"> リクエストがサーバーによって処理された時刻（精度100秒）正確性は、サーバ環境とNTPによって異なります。 </td> 
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
   <td colname="col3"> HTTPサーバーの応答のステータスを記録する、サーバーによって生成される数値コード </td> 
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
   <td colname="col3"> クライアントが送信するHTTPリファラーフィールドの内容 </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> ユーザーエージェント </td> 
   <td colname="col3"> HTTPサーバーにリクエストを行うために使用するデバイス </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0;+ Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> ドメインのクライアントCookie </td> 
   <td colname="col3"> サイトのすべてのユーザーのCookieの内容 </td> 
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

