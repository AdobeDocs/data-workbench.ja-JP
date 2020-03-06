---
description: Insightサーバー、リピーターまたは変換の管理アラートを設定する手順です。
solution: Insight
title: 管理アラートの構成設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理アラートの構成設定{#administrative-alerts-configuration-settings}

Insightサーバー、リピーターまたは変換の管理アラートを設定する手順です。

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
   <td colname="col2"> カテゴリの名前。 「デフォルト」のカテゴリが必要です。 この表のエラーカテゴリを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーカテゴリ </td> 
   <td colname="col2"> エラーをエラー分類ファイルと組み合わせて分類できます。 各エラーカテゴリには、独自の受信者セットと独自のスロットル遅延を設定できます。 例えば、スロットル遅延が0のクリティカルカテゴリを作成し、すべての重大なエラーが「受信者」リストで指定した受信者に即座に電子メールで送信されるようにすることができます。 エラー分類ファイル内のサブ文字列と一致しないエラーは、デフォルトのカテゴリに割り当てられます。 新しいカテゴリを追加するには、数値を右クリックし、新規追加/エラーカ <span class="uicontrol"> テゴリを </span> クリ <span class="uicontrol"> ックしま </span>す。 また、右クリックアクションを使用して、コピーまたは削除することもできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーの分類ファイル </td> 
   <td colname="col2"> <p>各アラートの分類に使用するファイルの名前。 このファイルはメモ帳を使用して作成します。 このファイルの各行には、タブで区切った3つの列が必要です。 最初の列は、エラー時に一致する文字列です。 ^記号は先頭に一致し、$は文字列の末尾に一致します。その他のすべての文字は文字どおりに一致します。 2番目の列は、一致するエラーのカテゴリで、エラーのカテゴリです。 3つ目は代替メッセージで、送信される電子メールの実際のエラーメッセージの前に付加されます。 ファイルが指定されていない場合、すべてのエラーがデフォルトとして分類されます。 </p> <p>このファイルの例を確認するには、Lookupsディレクトリ内の <span class="filepath"> Error Categories.txtフ </span> ァイルを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元 </td> 
   <td colname="col2"> <p>電子メールメッセージの「送信者」パラメーターに表示されるアドレス。 </p> <p>例： <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小ディスク容量(MB) </td> 
   <td colname="col2"> サーバーが使用するディレクトリ内の使用可能なディスクストレージがこの値を下回ると、サーバーは電子メールアラートを生成します。 デフォルト値は 1000 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーの警告タイムアウト（分） </td> 
   <td colname="col2"> <p>この時間枠内に、設定済みで以前に接続されたSensorからデータを受信しなかった場合、サーバーは電子メール <span class="wintitle"> アラート </span> を生成します。 デフォルト値は 15 です。 </p> <p> <p>注意： センサ <span class="wintitle"> ーの </span> 警告タイムアウトは、センサーへの既存の接続が切断された場合に <span class="wintitle"> のみ機 </span> 能します。 サーバーのサービスが停止して再起動され、Sensorが接 <span class="wintitle"> 続さ </span> れない場合、サーバーは電子メールアラートを生成しません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーアドレス </td> 
   <td colname="col2"> <p>送信電子メールのSMTPサーバーのアドレス。 </p> <p>例： <span class="filepath"> mail.mycompany.com </span></p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーパスワード </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールの送信にログインが必要でない限り、このパラメータはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーユーザー </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザーID/名前。 メールの送信にログインが必要でない限り、このパラメータはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> スロットル遅延（秒） </td> 
   <td colname="col2"> 電子メールを送信するために、そのカテゴリの2つのエラーの間に経過する必要がある最小秒数。 値を0に設定すると、電子メールが直ちに送信されます。 </td> 
  </tr> 
 </tbody> 
</table>

