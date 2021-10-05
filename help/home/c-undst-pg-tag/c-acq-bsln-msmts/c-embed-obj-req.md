---
description: ブラウザがページのHTMLを要求した後、ブラウザは、そのページのHTMLで参照されている埋め込みオブジェクトを Web サーバにリクエストし、ブラウザが表示するページに入力する。
title: 埋め込みオブジェクトリクエスト（ページタグ）の取得
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 6%

---

# 埋め込みオブジェクトリクエスト（ページタグ）の取得{#acquiring-embedded-object-requests-page-tags}

ブラウザがページのHTMLを要求した後、ブラウザは、そのページのHTMLで参照されている埋め込みオブジェクトを Web サーバにリクエストし、ブラウザが表示するページに入力する。

このような埋め込みオブジェクトリクエストは、イメージファイルや JavaScript ファイルに対する最も一般的なリクエストですが、現在、インターネット上で使用されている埋め込みオブジェクトの種類は、数百、数千です。 これらの埋め込みオブジェクトリクエストの多くは、通常、インターネットサイトのビジネスアクティビティの分析やレポートに役立ちません。広告の提示やサイト活動の測定など、特定のビジネス目的を持たない限り、こうした要求の多くは獲得には望ましくありません。

例えば、画像は広告であり、広告が訪問者に印象付けられたことを知りたい場合があります。 JavaScript スニペットを使用して、特定のブラウザーに特定の特性があるという測定を行い、[!DNL Sensor] に戻して獲得することができます。 サイトの各ページには、10 個または 100 個の埋め込みオブジェクトリクエストが含まれています。 サイトがこれらの各要求のログ情報を保存する場合、将来の分析に使用できるログデータを保持するために必要なデータストレージの量に、要求された各ページの埋め込みオブジェクト要求の数が乗算されます。 このため、[!DNL Site] を使用すると、分析に重要なリクエストを保持し、他のリクエストを破棄してから、不要なストレージコストを発生させることができます。

[!DNL Sensor] のコンテンツタイプフィルタリング機能（埋め込みオブジェクトリクエスト URL のクエリ文字列に&quot;Log=1&quot;を付加）で提供される上書き機能を使用すると、サイト管理者がそのタイプのリクエスト（例えば、すべての `<image>` リクエスト）を保存する必要がなく、特定の埋め込みオブジェクトリクエストと関連測定データを取得できます。

[!DNL Sensor] は、Web サーバーで作成された埋め込みオブジェクトリクエストごとに、次の表の測定データを収集しま [!DNL Sensor] す。これは、フィルターを除外するように設定されていない場合や、フィルターが上書きされた場合です。収集された情報は、x-trackingid または cs(cookie) ログフィールドエントリを通じて、訪問者とセッション、およびそれ以降のセッションに関連します。

<table id="table_11BE08A798E743EC8E76F738F0CE5884">
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
   <td colname="col3"> 最初のリクエスト時に <span class="wintitle"> Sensor </span> によってユーザーのブラウザーに配置された Cookie から読み取られた識別子 </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>日付 </p> <p>時間 </p> </td>
   <td colname="col2"> タイムスタンプ </td>
   <td colname="col3"> リクエストがサーバーによって処理された時刻（100 ns の精度）。精度は、サーバ環境と NTP に依存します。 </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> コンテンツタイプ </td>
   <td colname="col3"> サーバーから返されたオブジェクトのタイプ </td>
   <td colname="col4"> text/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> HTTP 応答ステータスコード </td>
   <td colname="col3"> HTTP サーバーの応答のステータスを示す、サーバーによって生成される数値コード </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI ステム </td>
   <td colname="col3"> クライアントが要求した URI の「ステム」部分 </td>
   <td colname="col4"> pagedir/page.asp </td>
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
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 参照 URL </td>
   <td colname="col3"> クライアントから送信された HTTP リファラーフィールドの内容 </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> ユーザーエージェント </td>
   <td colname="col3"> HTTP サーバーに要求を送信する際に使用するデバイス </td>
   <td colname="col4"> <p>Mozilla/4.0 以降 ( 互換；+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> ドメインからのクライアント cookie </td>
   <td colname="col3"> サイトに対するユーザーのすべての Cookie の内容 </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> クエリー文字列 </td>
   <td colname="col3"> クライアントが要求した URI のクエリー文字列部分（ある場合） </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
