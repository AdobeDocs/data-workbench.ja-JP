---
description: センサは、インストールされたWebサーバに対して行われたページリクエスト(GETリクエスト)に対するすべての測定データを取得します。
title: ページリクエストデータの取得
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 6%

---

# ページリクエストデータの取得{#acquiring-page-request-data}

センサは、インストールされたWebサーバに対して行われたページリクエスト(GETリクエスト)に対するすべての測定データを取得します。

[!DNL Sensor] は、Webサーバ上で動作するWebサーバソフトウェアのインスタンスから、Webサーバのアプリケーションプログラミングインターフェイスを介して、この測定データを直接取得します。[!DNL Sensor] は、webサーバーで生成されたログファイルにアクセスしません。実際、[!DNL Sensor]とData Workbenchサーバーがインストールおよびテストされた後は、データ収集に影響を与えることなく、Webサーバーのネイティブログ機能を無効にできます。 多くの場合、Webサーバマシン自体のローカルディスクに対するファイルのログ記録を無効にすると、Webサーバマシンのローカルディスクにこの情報を記録するのに必要な固定ディスクI/Oが比較的大量にあるので、Webサーバのページ提供容量が向上します。

[!DNL Sensor] は、各webサーバープロセスと仮想webサーバープロセス（該当する場合）から測定とweb要求データを直接収集し、固定ディスクバッキングを持つフォールトトレラントなメモリキューであるキューファイルに一時的に書き込みます。Sensor Transmitterサービス（またはプラットフォームに応じたデーモン）は、キューファイルからデータを取得し、圧縮して暗号化してから、長期ストレージ用にData Workbenchサーバーに送信します。 [!DNL Sensor]を使用すると、データは、送信を妨げるネットワークやその他の問題が発生した場合にのみ、Webサーバーマシンのキューファイルに蓄積されます。 キューファイルを使用すると、ネットワークやシステムの障害によってData Workbenchサーバーにリアルタイムでデータを送信できない場合に、Webリクエストデータを数時間から数日にわたって効率的にローカルに保存してデータを保護できます。

[!DNL Sensor] は、物理および論理の各Webサーバープロセスから測定データを収集し、コンテンツタイプ別にフィルタリングし、圧縮、暗号化して、Data Workbenchサーバーにストリーミングします。

次の表に、[!DNL Sensor]が取得するログ情報のフィールドを示します。このフィールドは、[!DNL Sensor’s]設定ファイルに基づいて除外されないGETリクエストごとに使用されます。

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
   <td colname="col3"> 訪問者の最初のリクエストに対して<span class="wintitle">センサー</span>がユーザーのブラウザーに配置したCookieから読み取った識別子 </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP応答ステータスコード </td> 
   <td colname="col3"> HTTPサーバーの応答のステータスをメモする、サーバーによって生成される数値コード </td> 
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URIステム </td> 
   <td colname="col3"> クライアントが要求したURIのステム部分 </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td> 
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
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 参照 URL </td> 
   <td colname="col3"> クライアントから送信されたHTTPリファラーフィールドの内容 </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com  </span> </td> 
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
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>
