---
description: Insightサーバー、リピーターまたは変換に関する管理アラートを設定する手順です。
solution: Analytics
title: 管理アラートの設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---


# 管理アラートの設定{#administrative-alerts-configuration-settings}

Insightサーバー、リピーターまたは変換に関する管理アラートを設定する手順です。

次のファイルのパラメーターを設定します。

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> カテゴリ </td> 
   <td colname="col2"> カテゴリの名前。 デフォルトのカテゴリが必要です。 この表のエラーカテゴリを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーカテゴリ </td> 
   <td colname="col2"> エラーをエラー分類ファイルと共に分類できます。 各エラーカテゴリには、独自の受信者セットと独自のスロットル遅延を設定できます。 例えば、スロットル遅延が0の重大なカテゴリを作成すると、重大なエラーが発生するたびに、受信者リストで指定された受信者に即座に電子メールで送信されます。 エラーカテゴリー化ファイル内のサブ文字列と一致しないエラーは、デフォルトカテゴリに割り当てられます。 新しいカテゴリを追加するには、数値を右クリックし、 <span class="uicontrol"> 新規 </span> / <span class="uicontrol"> エラーカテゴリをクリックし </span>ます。 右クリック操作を使用して、コピーまたは削除することもできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラー分類ファイル </td> 
   <td colname="col2"> <p>各アラートの分類に使用するファイルの名前。 このファイルはメモ帳を使用して作成します。 このファイルの各行には、タブで区切られた3つの列が必要です。 最初の列はエラー時に一致する文字列です。 ^記号は先頭に一致し、$は文字列の末尾に一致します。その他のすべての文字は、文字どおりに一致します。 2番目の列は、一致するエラーのカテゴリです。このエラーカテゴリは、「エラー」に表示されます。 3つ目は代替メッセージで、送信される電子メールの実際のエラーメッセージの前に付加されます。 ファイルを指定しない場合、すべてのエラーはデフォルトとして分類されます。 </p> <p>このファイルの例については、Lookupsディレクトリの <span class="filepath"> Errorカテゴリ.txt </span> ファイルを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元 </td> 
   <td colname="col2"> <p>電子メールメッセージの「送信者」パラメーターに表示されるアドレス。 </p> <p>例： <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小ディスク容量(MB) </td> 
   <td colname="col2"> サーバが使用するディレクトリの使用可能なディスクストレージがこの値を下回ると、サーバは電子メールアラートを生成します。 デフォルト値は 1000 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーアラートタイムアウト（分） </td> 
   <td colname="col2"> <p>サーバーは、設定済みで以前に接続した <span class="wintitle"> センサーからこの時間内にデータを受け取らない場合、電子メールアラート </span> を生成します。 デフォルト値は 15 です。 </p> <p> <p>注意： <span class="wintitle"> センサー </span> 警告タイムアウトは、センサーへの既存の接続が切断された場合にのみ機能 <span class="wintitle"></span> します。 サーバーのサービスが停止して再起動され、 <span class="wintitle"> Sensorが接続しない場合、サーバー </span> では電子メールアラートは生成されません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーアドレス </td> 
   <td colname="col2"> <p>送信電子メールのSMTPサーバーのアドレスです。 </p> <p>例： <span class="filepath"> mail.mycompany.com </span></p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server Password </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールの送信にログインが必要な場合を除き、このパラメーターはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーユーザー </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザーID/ユーザー名です。 メールの送信にログインが必要な場合を除き、このパラメーターはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Throttle Delay (secs) </td> 
   <td colname="col2"> 電子メールを送信するために、そのカテゴリ内の2つのエラーの間に経過する必要がある最小秒数。 値0は電子メールを直ちに送信します。 </td> 
  </tr> 
 </tbody> 
</table>

