---
description: Insightサーバー、リピーターまたは変換の管理アラートを設定する手順です。
title: 管理アラートの設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# 管理アラートの設定{#administrative-alerts-configuration-settings}

Insightサーバー、リピーターまたは変換の管理アラートを設定する手順です。

次のファイルのパラメーターを入力します。

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
   <td colname="col2"> エラー分類ファイルと組み合わせてエラーを分類できます。 各エラーカテゴリには、独自の受信者セットと独自のスロットル遅延を設定できます。 例えば、スロットル遅延が0の重大カテゴリを作成して、重大なエラーがすべて受信者リストで指定された受信者に即座に電子メールで送信されるようにできます。 エラーカテゴリー化ファイル内のサブ文字列と一致しないエラーは、デフォルトカテゴリに割り当てられます。 新しいカテゴリを追加するには、数値を右クリックし、<span class="uicontrol">新規追加</span> / <span class="uicontrol">エラーカテゴリ</span>をクリックします。 右クリックのアクションを使用して、コピーまたは削除することもできます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラー分類ファイル </td> 
   <td colname="col2"> <p>各アラートの分類に使用するファイルの名前。 このファイルはメモ帳を使用して作成します。 このファイルの各行には、タブで区切られた3つの列が必要です。 最初の列は、エラーに一致する文字列です。 ^記号は先頭に一致し、$は文字列の末尾に一致します。その他の文字はすべてリテラルと一致します。 2番目の列は、一致するエラーのカテゴリで、エラーカテゴリにあります。 3つ目は代替メッセージで、送信されるEメールの実際のエラーメッセージの前に付けられます。 ファイルを指定しない場合、すべてのエラーがデフォルトとして分類されます。 </p> <p>このファイルの例を確認するには、 Lookupsディレクトリの<span class="filepath"> Error Categories.txt </span>ファイルを参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元 </td> 
   <td colname="col2"> <p>電子メールメッセージの「from」パラメーターに表示されるアドレス。 </p> <p>例：<span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小ディスク容量(MB) </td> 
   <td colname="col2"> サーバーが使用する任意のディレクトリの使用可能なディスクストレージがこの値を下回ると、サーバーは電子メールアラートを生成します。 デフォルト値は 1000 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーアラートのタイムアウト（分） </td> 
   <td colname="col2"> <p>この期間内に設定済みで接続済みの<span class="wintitle">センサー</span>からデータを受信しない場合、サーバーは電子メールアラートを生成します。 デフォルト値は 15 です。 </p> <p> <p>注意： <span class="wintitle">センサー</span>アラートタイムアウトは、<span class="wintitle">センサー</span>への既存の接続が切断された場合にのみ機能します。 サーバーのサービスが停止して再起動され、<span class="wintitle">センサー</span>が接続されない場合、サーバーはEメールアラートを生成しません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーアドレス </td> 
   <td colname="col2"> <p>送信電子メールのSMTPサーバーのアドレス。 </p> <p>例：<span class="filepath"> mail.mycompany.com </span></p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーのパスワード </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールを送信するためにログインが必要でない限り、このパラメーターはオプションです。 </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバーユーザー </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザーID/名前。 メールを送信するためにログインが必要でない限り、このパラメーターはオプションです。 </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> スロットル遅延（秒） </td> 
   <td colname="col2"> 電子メールを送信するために、そのカテゴリの2つのエラーの間に経過する必要がある最小秒数。 値0を指定すると、電子メールが直ちに送信されます。 </td> 
  </tr> 
 </tbody> 
</table>
