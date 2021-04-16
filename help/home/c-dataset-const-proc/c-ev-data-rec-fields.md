---
description: データセットを構築する際に Data Workbench サーバーで処理できるデータフィールドについて取り上げます。
title: イベントデータレコードフィールド
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 88%

---

# イベントデータレコードフィールド{#event-data-record-fields}

データセットを構築する際に Data Workbench サーバーで処理できるデータフィールドについて取り上げます。

* [イベントデータについて](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [ベースラインイベントデータレコードフィールド](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [派生フィールド](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## イベントデータについて  {#section-3a0705f8c1824017aa4effed9903efbe}

データセット構築用のイベントデータは、ログソースと呼ばれるファイル内に存在します。各データレコードが 1 件のトランザクションレコード、またはタイムスタンプを持った 1 回のイベントの発生を表していることから、ログソース内のデータは「イベントデータ」と呼ばれます。

ログソースのイベントデータは[!DNL Sensors]によってリアルタイムに収集されます。 [!DNL Sensors]によってHTTPサーバーやアプリケーションサーバーから収集されたイベントデータはData Workbenchサーバーに送信され、そこで、圧縮されたログ( [!DNL .vsl])ファイルに変換されます。 フラットファイル、XML ファイルまたは ODBC データソースに存在するイベントデータを読み取る Data Workbench サーバーは、こうした様々な形式のファイルから決まった一連のデータフィールドを抽出するよう設定されたデコーダーの役割を担います。

以下の節では、[!DNL Sensors]によって収集され、Data Workbenchサーバーで読み取って使用できるデータフィールド(イベントデータレコードフィールドまたはログエントリフィールドと呼ばれます)について説明します。

>[!NOTE]
>
>フィールド名は、通常、W3C拡張ログファイル形式の命名規則に従います。 多くのフィールドには、その情報の取得元を表すプレフィックスが付いています。

* cs は、クライアントからサーバーへの通信を表します。
* sc は、サーバーからクライアントへの通信を表します。
* s は、サーバーからの情報を表します。
* c は、クライアントからの情報を表します。
* x は、アドビのソフトウェア製品によって生成された情報であることを表します。

## ベースラインイベントデータレコードフィールド {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

ログ([!DNL .vsl])ファイルには、[!DNL Sensors]によってサーバーから収集され、イベントセット構築プロセスでData Workbenchサーバーが使用するサーバーデータのフィールドが含まれます。 次の表は、[!DNL Sensor] によって記録される代表的なイベントデータレコードのフィールドの一覧です。

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>サーバーに対して送信されたリクエストに含まれているクライアントの IP アドレス。 </p> <p> 例：207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともに送信された cookie。 </p> <p> 例：v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともにサーバーに送信された HTTP リファラー文字列。 </p> <p> 例：<span class="filepath">http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>クライアントによってリクエストとともにサーバーに送信された文字列。そのクライアントに該当するユーザーエージェントのタイプを表します。 </p> <p> 例：Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>HTTP リクエストのメソッドのタイプ。 </p> <p> 例：GET </p> <p> リファレンス：<span class="filepath">http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>URI のクエリー文字列部分（ステム + クエリー文字列 = URI）。疑問符（?）で始まり、名前と値のペアを含んでいる場合もあります。複数のペアが含まれている場合は、アンパサンド（&amp;）で区切って指定されます。 </p> <p> 例：page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>URI のステム部分（ステム + クエリー文字列= URI）。ステムは、サーバー上の要求されたリソースに対する実際のパスまたは論理パスです。 </p> <p> 例：<span class="filepath">/index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>クライアントから要求されているとしてサーバーが報告したリソースのコンテンツタイプ。 </p> <p> 例：text/html、image/png、image/gif、video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>リクエストへの応答としてサーバーからクライアントに送信されたデータのバイト数。 </p> <p> 例：4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>サーバーからクライアントに返されたステータスコード。 </p> <p> 例：200 </p> <p> リファレンス：<span class="filepath">http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>要求されたリソースのホストの完全修飾ドメイン名または IP アドレス。 </p> <p> 例：<span class="filepath">www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>リクエストの時点でクライアントが属しているすべての制御実験の名前とグループのリスト。 </p> <p> 例：VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>リクエストがサーバーによって受信された日付と時刻（GMT）。時刻は、1600 年 1 月 1 日からの 100 ナノ秒数で表されます。 </p> <p> 例：2005 年 9 月 13 日 火曜日 11:28:52.0000000 の場合、x-timestamp 値は 127710989320000000 となります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>持続 Cookie に検出されたブラウザーの一意の ID を表す 64 ビットの 16 進数値。<span class="wintitle">Sensor</span> によって設定され、サーバーへのリクエストとともにクライアントから提供されます。 </p> <p> 例：42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 派生フィールド  {#section-b6c57ee2aa31469fbd5dab90e52bc677}

次の表は、ベースラインイベントデータレコードのフィールドから Data Workbench サーバーが生成する派生フィールドの例を示しています。

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> cookie に含まれる特定の名前と値のペアの値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>HTTP 参照元 URI のドメイン名または IP アドレス。 </p> <p> <p>注意：このフィールドは読み取り専用です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>リファラーのホスト名全体。 </p> <p> 例：cs(referrer) が <span class="filepath">http://my.domain.com/my/page</span> である場合、cs(referrer-host) は <span class="filepath">my.domain.com</span> になります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>リファラークエリー文字列の値。 </p> <p> <p>注意：cs(referrer)(name) フィールドを使用して、リファラークエリー文字列の値にアクセスすることはできません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>完全な URI（ステム + クエリー文字列 = URI 全体）。 </p> <p> 例：<span class="filepath">/shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>指定された名前に関連付けられている値。指定された名前に対して複数の値が存在する場合、その中の最後の値が返されます。 </p> 例： 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> <span class="filepath">/shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd</span> という URI に対し、cs-uri-query(product3) からは「cd」が返されます。 </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> <span class="filepath">/shopping/checkout.html?product1=8Track&amp;product1=casette</span> という URI に対し、<span class="wintitle">cs-uri-query(product1)</span> からは「casette」が返されます。 </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> 1970 年 1 月 1 日からの秒数で表される x-timestamp。このフィールドは、x-unixtime と呼ばれることもあります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日付 </td> 
   <td colname="col2"> YYYY-MM-DD 形式の x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> HH:MM:SS 形式の x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>データセットの <span class="filepath">Transformation.cfg</span> ファイルに指定されたローカルタイムゾーンに変換した x-timestamp。YYYY-MM-DD HH:MM:SS.mmm という形式になります。 </p> <p> <p>注意：<span class="filepath">Log Processing.cfg</span> ファイルで時刻変換（x-local-timestring など）を定義することもできます。詳しくは、<a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">ログ処理設定ファイル</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>特定のログエントリのログソースに対応する識別子。この識別子を記録するためには、<span class="wintitle">Sensor</span>、ログファイルまたは ODBC データソースを定義するときに、<span class="filepath">Log Processing.cfg</span> ファイルの <span class="wintitle">Log Source ID</span> フィールドに識別子を指定する必要があります。詳しくは、<a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">ログ処理設定ファイル</a>を参照してください。 </p> <p> 例：from VSensor01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> <span class="wintitle">Sensor</span> データソースのマスクパターン（<span class="filepath">.vsl</span> ファイル名から派生）。名前の形式が <span class="filepath">YYYYMMDD-SENSORID.VSL</span> であるファイルの x-mask は SENSORID になります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> YYYY-MM-DD HH:MM:SS.mmm 形式の x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> x-timestamp から派生した 10 進数の UNIX 時間。 </td> 
  </tr> 
 </tbody> 
</table>

サーバー上の [!DNL Sensor] は、有効な HTTP リクエスト（または応答）ヘッダーから、またはサーバーの API を介して提供される変数から、イベントデータのフィールドを収集することができます。こうしたデータフィールドを収集するには、[!DNL txlogd.conf] の [!DNL Sensor] 設定ファイルに目的のヘッダーフィールドまたは変数を指定する必要があります。詳しくは、『*Data Workbench [!DNL Sensor] ガイド*』を参照してください。
