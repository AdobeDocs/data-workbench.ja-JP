---
description: ページのHTMLがブラウザによって要求された後、ブラウザは、そのページのHTMLで参照されている埋め込みオブジェクトをWebサーバに要求し、ブラウザが示すページに入力します。
solution: Analytics
title: 埋め込みオブジェクトリクエスト（ページタグ）の取得
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 6%

---


# 埋め込みオブジェクトリクエスト（ページタグ）の取得{#acquiring-embedded-object-requests-page-tags}

ページのHTMLがブラウザによって要求された後、ブラウザは、そのページのHTMLで参照されている埋め込みオブジェクトをWebサーバに要求し、ブラウザが示すページに入力します。

このような埋め込みオブジェクトの要求は、イメージファイルやJavaScriptファイルの要求として最も一般的ですが、現在インターネット上で使用されている埋め込みオブジェクトの数は数百、何千もです。 これらの埋め込みオブジェクトリクエストの多くは、インターネットサイトのビジネスアクティビティの分析やレポートに役立ちません。広告の提示やサイトアクティビティの測定など、特定のビジネス目的を持たない限り、このような要求の多くは獲得に望ましくありません。

例えば、画像が広告であり、その広告が訪問者に印象付けられたことを知りたい場合があります。 特定のブラウザーに特定の特性がある測定を行い、その特性をに返して獲得用に渡すために、JavaScriptスニペットが使用されている場合があ [!DNL Sensor] ります。 サイトの各ページには、10または100個の埋め込みオブジェクトリクエストが含まれます。 サイトがこれらの各リクエストのログストレージを保存している場合、今後の分析に使用できるログデータを維持するために必要なデータ情報の量に、要求された各ページの埋め込みオブジェクト要求の数を掛けます。 このため、 [!DNL Site] 不要なストレージコストが発生する前に、分析にとって重要なリクエストを維持し、他のリクエストを破棄できます。

コンテンツタイプのフィルタリング機能に備わるオーバーライド機能(埋め込みオブジェクトリクエストURLのクエリ列に「Log=1」を付加)を使用すると、サイト管理者がそのタイプのリクエスト（例えば、全てのリクエスト）を保存する必要なく、特定の埋め込みオブジェクトリクエストと関連する測定データを取得できる。 [!DNL Sensor]`<image>`

[!DNL Sensor] webサーバーで行われる埋め込みオブジェクトリクエストごとに、次の表の測定データを収集します。これは、このリクエストをフィルター処理するように設定されていないか、フィルターが上書きされている場合です。 [!DNL Sensor] 収集された情報は、x-trackingidまたはcs(cookie)ログフィールドエントリを通じて、訪問者、セッション、および以降のセッションに関連します。

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
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
   <td colname="col3"> 最初のリクエスト時にSensorによってユーザーのブラウザーに配置されたcookieから読み取ら <span class="wintitle"></span> れた識別子 </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> text/html </td> 
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
   <td colname="col3"> クライアントが要求したURIの「ステム」部分 </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 参照 URL </td> 
   <td colname="col3"> クライアントから送信されるHTTP転送者フィールドの内容 </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> ユーザーエージェント </td> 
   <td colname="col3"> HTTPサーバーにリクエストを行うために使用するデバイス </td> 
   <td colname="col4"> <p>Mozilla/4.0+(compatible;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> ドメインからのクライアントcookie </td> 
   <td colname="col3"> サイトに対するすべてのユーザーのCookieの内容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> クエリー文字列 </td> 
   <td colname="col3"> クライアントが要求したURIのクエリ文字列部分（存在する場合） </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

