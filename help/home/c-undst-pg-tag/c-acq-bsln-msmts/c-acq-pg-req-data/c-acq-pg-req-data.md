---
description: センサーは、インストール先の Web サーバーに対して行われたページリクエスト (GETリクエスト ) に対して実行されるすべての測定データを取得します。
title: ページリクエストデータの取得
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 6%

---

# ページリクエストデータの取得{#acquiring-page-request-data}

{{eol}}

センサーは、インストール先の Web サーバーに対して行われたページリクエスト (GETリクエスト ) に対して実行されるすべての測定データを取得します。

[!DNL Sensor] は、Web サーバ上で稼働する Web サーバソフトウェアのインスタンスまたはインスタンスから、Web サーバのアプリケーションプログラミングインターフェイスを通じて、この測定データを直接取得します。 [!DNL Sensor] は、web サーバーで生成されたログファイルにアクセスしません。 実際には、 [!DNL Sensor] data workbench サーバーがインストールおよびテストされている場合、web サーバーのネイティブログ機能は、データ収集に影響を与えることなく無効にできます。 多くの場合、Web サーバマシン自体のローカルディスクへのファイルのログ記録を無効にすると、Web サーバマシンのローカルディスクにこの情報を記録するのに必要な固定ディスク I/O が比較的大量にあるので、Web サーバのページ配信容量が向上します。

[!DNL Sensor] は、各 web サーバプロセスと仮想 web サーバプロセス（該当する場合）から測定と web 要求データを直接収集し、固定ディスクバッキングを持つフォールトトレラントなメモリキューであるキューファイルに一時的に書き込みます。 Sensor Transmitter サービス（またはプラットフォームに応じたデーモン）は、キューファイルからデータを取得し、圧縮して暗号化してから、長期保存用に Data Workbench サーバーに送信します。 を使用 [!DNL Sensor]の場合、データは、ネットワークやその他の問題が発生して送信を妨げている場合にのみ、Web サーバーマシンのキューファイルに蓄積されます。 キューファイルを使用すると、ネットワークまたはシステムの障害によって Data Workbench サーバーにデータをリアルタイムで送信できない場合に、Web リクエストデータを数時間から数日にわたって効率的にローカルに保存し、データを保護できます。

[!DNL Sensor] は、物理および論理の各 Web サーバープロセスから測定データを収集し、コンテンツタイプ別にフィルタリングし、圧縮し、暗号化して、Data Workbench サーバーにストリーミングします。

次の表に、 [!DNL Sensor] に基づいてフィルタリングされないGETリクエストごとに [!DNL Sensor’s] 設定ファイル：

<table id="table_5F65474150EC41648B35D0B031FB9B15">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C 名 </th>
   <th colname="col2" class="entry"> 収集されたデータ </th>
   <th colname="col3" class="entry"> 説明 </th>
   <th colname="col4" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> トラッキング識別子（個別訪問者） </td>
   <td colname="col3"> ユーザーのブラウザーに配置された Cookie から読み取られた識別子。 <span class="wintitle"> センサー </span> 訪問者の最初のリクエスト時 </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
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
   <td colname="col4"> text/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> HTTP 応答ステータスコード </td>
   <td colname="col3"> HTTP サーバーの応答のステータスをメモする、サーバーによって生成される数値コード </td>
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI ステム </td>
   <td colname="col3"> クライアントによってリクエストされた URI のステム部分 </td>
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td>
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
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 参照 URL </td>
   <td colname="col3"> クライアントから送信される HTTP リファラーフィールドの内容 </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
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
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
