---
description: Insight サーバー、リピーターまたは変換の管理アラートを設定する手順です。
title: 管理アラートの設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# 管理アラートの設定{#administrative-alerts-configuration-settings}

{{eol}}

Insight サーバー、リピーターまたは変換の管理アラートを設定する手順です。

次のファイルにあるパラメーターを入力します。

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
   <td colname="col2"> カテゴリの名前。 デフォルトのカテゴリは必須です。 この表のエラーカテゴリを参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーカテゴリ </td> 
   <td colname="col2"> エラー分類ファイルと組み合わせてエラーを分類できます。 各エラーカテゴリには、独自の受信者セットと独自のスロットル遅延を設定できます。 例えば、スロットル遅延が 0 の重大カテゴリを作成して、重大なエラーがすべて受信者リストで指定された受信者に即座に電子メールで送信されるようにします。 エラー分類ファイル内のサブ文字列と一致しないエラーは、デフォルトカテゴリに割り当てられます。 新しいカテゴリを追加するには、数値を右クリックし、 <span class="uicontrol"> 新規追加 </span> &gt; <span class="uicontrol"> エラーカテゴリ </span>. 右クリックのアクションを使用してコピーまたは削除することもできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラー分類ファイル </td> 
   <td colname="col2"> <p>各アラートの分類に使用するファイルの名前。 このファイルはメモ帳を使用して作成します。 このファイルの各行には、タブで区切られた 3 つの列が必要です。 最初の列は、エラーに一致する文字列です。 ^記号は先頭に一致し、$は文字列の末尾に一致します。その他の文字はすべてリテラルとして一致します。 2 番目の列は、一致するエラーのカテゴリで、[ エラーのカテゴリ ] にあります。 3 つ目は代替メッセージで、送信される E メールの実際のエラーメッセージの前に付きます。 ファイルを指定しない場合、すべてのエラーがデフォルトとして分類されます。 </p> <p>このファイルの例については、 <span class="filepath"> Error Categories.txt </span> ファイルを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元 </td> 
   <td colname="col2"> <p>電子メールメッセージの「from」パラメーターに表示されるアドレス。 </p> <p>例： <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小ディスク容量 (MB) </td> 
   <td colname="col2"> サーバーが使用するディレクトリの使用可能なディスクストレージがこの値を下回ると、サーバーは電子メールアラートを生成します。 デフォルト値は 1000 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーアラートタイムアウト（分） </td> 
   <td colname="col2"> <p>設定済みで以前に接続されたからデータを受信しなかった場合、サーバーは電子メールアラートを生成します <span class="wintitle"> センサー </span> を設定します。 デフォルト値は 15 です。 </p> <p> <p>注意：  <span class="wintitle"> センサー </span> アラートタイムアウトは、 <span class="wintitle"> センサー </span> が削除されました。 サーバーのサービスが停止し、再起動された場合、 <span class="wintitle"> センサー </span> 接続しない場合、サーバーは e メールアラートを生成しません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーアドレス </td> 
   <td colname="col2"> <p>送信電子メール用の SMTP サーバーのアドレス。 </p> <p>例： <span class="filepath"> mail.mycompany.com </span></p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーのパスワード </td> 
   <td colname="col2"> <p>SMTP サーバーにログインするためのパスワードです。 メールの送信にログインが必要でない場合、このパラメーターはオプションです。 </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーユーザー </td> 
   <td colname="col2"> <p>SMTP サーバーにログインするためのユーザー ID/名前。 メールの送信にログインが必要でない場合、このパラメーターはオプションです。 </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> スロットル遅延（秒） </td> 
   <td colname="col2"> 電子メールを送信するために、そのカテゴリで 2 つのエラーの間に経過する必要がある最小秒数です。 値 0 を指定すると、電子メールが即座に送信されます。 </td> 
  </tr> 
 </tbody> 
</table>
