---
description: Sensorで記録されるベースラインイベントデータレコードフィールドに関する情報です。
title: ベースラインイベントデータレコードフィールド
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 72%

---

# ベースラインイベントデータレコードフィールド{#baseline-event-data-record-fields}

Sensorで記録されるベースラインイベントデータレコードフィールドに関する情報です。

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>サーバーに対して送信されたリクエストに含まれているクライアントの IP アドレス。 </p> <p>例：207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともに送信された cookie。 </p> <p>例：v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともにサーバーに送信された HTTP リファラー文字列。 </p> <p>例：http://www.mysite.net/cgi-bin/websearch?qry </p> <p>ページタグを使用している場合、cs(referrer)はタグ画像を含むドキュメントの完全なURL（HTTPやHTTPを含む）になります。 </p> <p>また、Apache(1.3、2.0、2.2)とIISのセンサーを設定して、要求に使用するポートを取り込むこともできます。このポートは、HTTP要求とHTTPS要求を識別できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともにサーバーに送信された文字列。そのクライアントに該当するユーザーエージェントのタイプを表します。 </p> <p>例：Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>HTTPリクエストのメソッドタイプ </p> <p>例：GET </p> <p>リファレンス：http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>URIのクエリー文字列部分（ステム+クエリー文字列= URI） </p> <p>疑問符（?）で始まり、名前と値のペアを含んでいる場合もあります。複数のペアが含まれている場合は、アンパサンド（&amp;）で区切って指定されます。 </p> <p>例：page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>URIのステム部分（ステム+クエリー文字列= URI） </p> <p>ステムは、サーバー上の要求されたリソースに対する実際のパスまたは論理パスです。 </p> <p>例：/index.asp </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>クライアントから要求されているとしてサーバーが報告したリソースのコンテンツタイプ。 </p> <p>例：text/html、image/png、image/gif、video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>リクエストへの応答としてサーバーからクライアントに送信されたデータのバイト数。。 </p> <p>例：4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>サーバーからクライアントに返されたステータスコード。 </p> <p>例：200 </p> <p>リファレンス：http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>要求されたリソースのホストの完全修飾ドメイン名または IP アドレス。 </p> <p>例：www.omniture.com </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>リクエストの時点でクライアントが属しているすべての制御実験の名前とグループのリスト。 </p> <p>例：Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>リクエストがサーバーによって受信された日付と時刻（GMT）。 </p> <p>時刻は、1600 年 1 月 1 日からの 100 ナノ秒数で表されます。 </p> <p>例：2005 年 9 月 13 日 火曜日 11:28:52.0000000 の場合、x-timestamp 値は 127710989320000000 となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>持続 Cookie に検出されたブラウザーの一意の ID を表す 64 ビットの 16 進数値。<span class="wintitle">Sensor</span> によって設定され、サーバーへのリクエストとともにクライアントから提供されます。 </p> <p>例：42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL data workbench server]は、ベースラインイベントデータレコードフィールドから多数の変数を派生させることができます。 詳しくは、『*データセット設定ガイド*』を参照してください。
