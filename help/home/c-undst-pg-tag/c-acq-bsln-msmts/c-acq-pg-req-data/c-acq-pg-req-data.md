---
description: Sensorは、インストールされたWebサーバーに対するページ要求（GET要求）で行われるすべての測定データを取得します。
solution: Analytics
title: ページリクエストデータの取得
topic: Data workbench
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ページリクエストデータの取得{#acquiring-page-request-data}

Sensorは、インストールされたWebサーバーに対するページ要求（GET要求）で行われるすべての測定データを取得します。

[!DNL Sensor] この測定データは、Webサーバーのアプリケーションプログラミングインターフェイスを通じて、Webサーバー上で実行されているWebサーバーソフトウェアのインスタンスから直接取得されます。 [!DNL Sensor] は、Webサーバーで生成されたログファイルにアクセスしません。 実際、Data Workbenchサーバーのイ [!DNL Sensor] ンストールおよびテストが完了すると、Webサーバーのネイティブログ機能を無効にしても、データ収集に影響を与えることはありません。 多くの場合、Webサーバーマシンのローカルディスクに対するファイルのログ記録を無効にすると、Webサーバーマシンのローカルディスクにこの情報を記録するために必要な固定ディスクI/Oが比較的大量に発生するので、Webサーバーのページ配信容量が向上します。

[!DNL Sensor] 各Webサーバープロセスおよび仮想Webサーバープロセス（該当する場合）から測定およびWeb要求データを直接収集し、Webサーバーマシン上の固定ディスクバッキングを持つ耐障害メモリキューであるキューファイルにデータを一時的に書き込みます。 Sensor Transmitterサービス（またはプラットフォームに応じたデーモン）は、キューファイルからデータを取得し、圧縮および暗号化してから、長期保存のためにData Workbenchサーバーに送信します。 を使用 [!DNL Sensor]すると、データは、送信を妨げるネットワークまたは他の問題が発生している場合にのみ、Webサーバーコンピューターのキューファイルに蓄積されます。 キューファイルを使用すると、ネットワークまたはシステム障害でデータをリアルタイムでData Workbenchサーバーに送信できない場合に、Webリクエストデータを数時間から数日間、効率的にローカルに保存し、データを保護できます。

[!DNL Sensor] 各物理および論理Webサーバープロセスから測定データを収集し、コンテンツタイプ別にフィルターし、圧縮、暗号化し、Data Workbenchサーバーにストリーミングします。

次の表に、設定ファイルに基づいて除外されない、各GET要求に対し [!DNL Sensor] てによって取得されるログ情報のフィールドを示 [!DNL Sensor’s] します。

<table id="table_5F65474150EC41648B35D0B031FB9B15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C名 </th> 
   <th colname="col2" class="entry"> 収集されたデータ </th> 
   <th colname="col3" class="entry"> 説明 </th> 
   <th colname="col4" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> トラッキング識別子（個別訪問者） </td> 
   <td colname="col3"> 訪問者の最初のリクエスト時にSensorによってユーザーのブラウザーに配置さ <span class="wintitle"> れた </span> cookieから読み取られた識別子 </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP応答ステータスコード </td> 
   <td colname="col3"> HTTPサーバーの応答のステータスを記録する、サーバーによって生成される数値コード </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URIステム </td> 
   <td colname="col3"> クライアントが要求したURIのステム部分 </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td> 
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
   <td colname="col3"> クライアントが送信するHTTPリファラーフィールドの内容 </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
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
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

