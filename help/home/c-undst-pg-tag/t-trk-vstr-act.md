---
description: Flashを使用して設計されたWebサイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して特に注意が必要です。
title: Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 7%

---

# Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡{#tracking-visitor-activity-within-flash-rich-media-content}

Flashを使用して設計されたWebサイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して特に注意が必要です。

[!DNL Flash]ActionScriptを使用すると、既存の[!DNL Flash]ムービーに簡単な変更を加えて、ボタンのクリックやマウスの動きなど、ムービーに対するすべての訪問者のインタラクションを追跡できます。

[!DNL Flash]ムービー内で訪問者のアクティビティの追跡を容易にするには、次の手順に従います。

1. ムービーに次のActionScriptコードを追加します。 このコードは、追跡する[!DNL Flash]ムービー内のイベントによって呼び出される関数を表します。

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

1. 次のActionScriptコードを、追跡するすべてのイベントに追加します。 このコードは、イベントに関するデータを取得するための関数呼び出しを表します。

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   この例では、 on(release)イベントの使用方法を示します。ただし、tag()関数は、on(press)、on(rollover)、on(rollout)、on(keypress)イベントなど、追跡する任意のイベントを通じて参照できます。

   \[[!DNL PUT_PAGE_NAME_HERE]\]プレースホルダーは、追跡するページまたはイベントの名前を表す文字列に置き換える必要があります。 \[[!DNL PUT_PAGE_NAME_HERE]\]変数は、手動で、または変数参照を使用して、[!DNL Flash]アプリケーション内のページまたはイベントの一意の名前を示すように変更できます。 \[[!DNL PUT_PAGE_NAME_HERE]\]プレースホルダーに代わる値は、単純な名前で構成することも、完全なURIと同様の階層構造を表すように構造化することもできます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobeでは、コードのデプロイメント前に、ビジネス要件と開発タスクの整合を容易にし、追加の開発サイクルの可能性を減らすために、ページ名とイベント名の仕様書をコンパイルすることをお勧めします。

1. 必要に応じて、追加の変数を収集し、[!DNL Flash]ムービーのページやイベントに関連付けることができます。 そのためには、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]プレースホルダーをアンパサンド(&amp;)で区切ったname=valueのペアのセットに置き換えます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   変数は、手動で、または変数参照を使用して変更でき、収集してページまたはイベントに関連付ける追加の属性を示します。 収集する該当する追加の変数がない場合は、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]を削除します。

   これで、[!DNL Flash]リッチメディアコンテンツ内の訪問者トラッキングの設定が完了しました。 イベントが呼び出されると、タグ[!DNL (PAGENAME,VARIABLES)]関数が呼び出され、次のファイルに対するHTTPリクエストが実行されます。 この関数は、[!DNL Flash]ムービー内で定義されたようにトリガーされる他の関数に加えて呼び出されます。

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

[!DNL Flash]タグActionScript関数によって生成されるHTTPリクエストにより、 [!DNL Flash]ムービー内の各イベントに関して次の情報が収集されます。 表の最後の行（W3C名前cs-uri-query）は、関数呼び出しで指定された追加の変数に対して収集された情報を表します。

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
   <td colname="col3"> 訪問者の最初のリクエストに対して<span class="wintitle">センサー</span>がユーザーのブラウザーに配置したCookieから読み取った識別子 </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日付 </p> <p>時間 </p> </td> 
   <td colname="col2"> タイムスタンプ </td> 
   <td colname="col3"> リクエストがサーバーによって処理された時刻（100 nsの精度）。精度は、サーバ環境とNTPに依存します。 </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> コンテンツタイプ </td> 
   <td colname="col3"> サーバーから返されるオブジェクトのタイプ </td> 
   <td colname="col4"> テキスト/HTML </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP応答ステータスコード </td> 
   <td colname="col3"> HTTPサーバーの応答のステータスをメモする、サーバーによって生成される数値コード </td> 
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
   <td colname="col2"> サーバーのドメイン名 </td> 
   <td colname="col3"> 要求を処理するWebサーバーのドメイン名 </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 参照 URL </td> 
   <td colname="col3"> クライアントから送信されたHTTPリファラーフィールドの内容 </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> ユーザーエージェント </td> 
   <td colname="col3"> HTTPサーバーに要求を送信するために使用するデバイス </td> 
   <td colname="col4"> Mozilla/4.0以降(互換；+MSIE+6.0;+Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> ドメインのクライアントcookie </td> 
   <td colname="col3"> サイトに対するユーザーのCookieの内容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> クエリー文字列 </td> 
   <td colname="col3"> クライアントが要求したURIのクエリー文字列部分（ある場合） </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
