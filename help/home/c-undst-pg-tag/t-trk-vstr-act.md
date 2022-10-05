---
description: Flashを使用して設計された Web サイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して、特に注意が必要です。
title: Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 7%

---

# Flash リッチメディアコンテンツ内の訪問者アクティビティの追跡{#tracking-visitor-activity-within-flash-rich-media-content}

{{eol}}

Flashを使用して設計された Web サイトでは、リッチメディアコンテンツ内で実行される訪問者のアクションのキャプチャに関して、特に注意が必要です。

使用 [!DNL Flash] ActionScriptでは、既存の [!DNL Flash] ムービー：ボタンのクリックやマウスの動きなど、ムービーとのすべての訪問者のインタラクションを追跡できます。

Web サイト内での訪問者アクティビティの追跡を容易にするには、 [!DNL Flash] ムービー、以下に示す手順に従ってください。

1. ムービーに次のActionScriptコードを追加します。 このコードは、 [!DNL Flash] 追跡するムービー。

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. という名前の空のファイルを作成します。 [!DNL flashtag.txt] Web サーバーにファイルを配置します。
1. 手順 1 の関数内で、\[[!DNL PATH_TO_WEB_SERVER]\] プレースホルダー。 [!DNL flashtag.txt] ファイル。 次に例を示します。

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 次のActionScriptコードを、追跡するすべてのイベントに追加します。 このコードは、イベントに関するデータを取得するために使用される関数呼び出しを表します。

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   この例では、 on(release) イベントの使用方法を示します。ただし、tag() 関数は、on(press)、on(rollover)、on(rollout)、on(keypress) イベントなど、追跡したいイベントを通じて参照できます。

   \[[!DNL PUT_PAGE_NAME_HERE]\] プレースホルダーは、追跡しているページまたはイベントの名前を表す文字列に置き換える必要があります。 \[[!DNL PUT_PAGE_NAME_HERE]\] 変数は、手動または変数参照を使用して、 [!DNL Flash] アプリケーション。 \[[!DNL PUT_PAGE_NAME_HERE]\] プレースホルダーは、単純な名前で構成することも、完全な URI と同様の階層構造を表すように構造化することもできます。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobeでは、コードのデプロイメント前に、ビジネス要件と開発タスクの整合を容易にし、追加の開発サイクルの可能性を減らすために、ページ名とイベント名の仕様書をコンパイルすることをお勧めします。

1. 必要に応じて、追加の変数を収集し、 [!DNL Flash] ムービー。 これを行うには、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\] プレースホルダー。name=value の組み合わせがアンパサンド (&amp;) で区切られています。 次に例を示します。

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   変数は、手動または変数参照を使用して変更でき、収集してページまたはイベントに関連付ける追加の属性を示します。 収集できる適用可能な追加の変数がない場合は、\[[!DNL PUT_ADDITIONAL_VAR_HERE]\].

   内での訪問者トラッキングの設定 [!DNL Flash] リッチメディアコンテンツが完了しました。 イベントが呼び出されると、タグ [!DNL (PAGENAME,VARIABLES)] 関数が呼び出され、次のファイルに対する HTTP リクエストが実行されます。 この関数は、 [!DNL Flash] ムービー：

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

結果の HTTP リクエスト [!DNL Flash] タグActionScript関数を使用すると、 [!DNL Flash] ムービー。 表の最後の行（W3C 名 cs-uri-query）は、関数呼び出しで指定された追加の変数について収集された情報を表します。

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C 名 </th>
   <th colname="col2" class="entry"> 収集されたデータ </th>
   <th colname="col3" class="entry"> 説明 </th>
   <th colname="col4" class="entry"> 例 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> トラッキング識別子（個別訪問者） </td>
   <td colname="col3"> ユーザーのブラウザーに配置された Cookie から読み取られた識別子。 <span class="wintitle"> センサー </span> 訪問者の最初のリクエスト時 </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>日付 </p> <p>時間 </p> </td>
   <td colname="col2"> タイムスタンプ </td>
   <td colname="col3"> リクエストがサーバーによって処理された時刻（100 ns の精度）。正確性はサーバ環境と NTP に依存 ) </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> コンテンツタイプ </td>
   <td colname="col3"> サーバーから返されたオブジェクトのタイプ </td>
   <td colname="col4"> テキスト/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> HTTP 応答ステータスコード </td>
   <td colname="col3"> HTTP サーバーの応答のステータスをメモする、サーバーによって生成される数値コード </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI ステム </td>
   <td colname="col3"> クライアントによってリクエストされた URI のステム部分 </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> クライアント IP </td>
   <td colname="col3"> 要求元クライアントの IP アドレス </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> サーバーのドメイン名 </td>
   <td colname="col3"> 要求を処理する Web サーバーのドメイン名 </td>
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 参照 URL </td>
   <td colname="col3"> クライアントから送信される HTTP リファラーフィールドの内容 </td>
   <td colname="col4"></td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> ユーザーエージェント </td>
   <td colname="col3"> HTTP サーバーにリクエストを送信する際に使用するデバイス </td>
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0;+Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> ドメインからのクライアント cookie </td>
   <td colname="col3"> サイトに対するユーザーのすべての Cookie の内容 </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> クエリー文字列 </td>
   <td colname="col3"> クライアントによってリクエストされた URI のクエリー文字列部分（存在する場合） </td>
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
