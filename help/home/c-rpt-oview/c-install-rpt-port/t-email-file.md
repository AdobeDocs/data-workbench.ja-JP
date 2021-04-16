---
description: レポートポータルへのアクセスと権限は、個々のユーザーアカウントとグループアカウントを使用して制御されます。
title: Email.asp ファイルの編集
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 5%

---

# Email.asp ファイルの編集{#edit-the-email-asp-file}

レポートポータルへのアクセスと権限は、個々のユーザーアカウントとグループアカウントを使用して制御されます。

新しいアカウントを追加したり、既存のアカウントを編集したりするたびに、そのアカウントに指定した電子メールアドレスに確認電子メールを送信し（[アカウントの操作](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)を参照）、[!DNL email.asp]ファイルで指定した電子メールアドレスにコピーできます。

>[!NOTE]
>
>通知電子メールは、アカウントの電子メールアドレスを指定し、[!DNL email.asp]ファイルを適切に設定した場合にのみ、アカウントユーザーに送信されます。 アカウントの通知電子メールを送信しない場合は、アカウントの電子メールフィールドを空白のままにします。

このファイルは`\*PortalName*\PortalASP`フォルダーにあります。

1. IISが実行されているマシン上で、[!DNL email.asp]ファイルをメモ帳などのテキストエディターで開きます。
1. 次の変数を設定します。

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> この変数用。.. </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>メッセージの送信に使用するSMTPサーバーのDNS名またはIPアドレス。 </p> <p>次に例を示します。<span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> SMTPサーバーが接続をリッスンするポートです。 これは通常、ポート25です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>メッセージの送信方法を示します。 値は以下のとおりです。 </p> <p>1 — ローカルにインストールされたSMTPサービスを使用してメッセージを送信します。 スクリプトを実行するコンピューターにSMTPサービスがインストールされている場合は、この値を使用します。 </p> <p>2 — ネットワーク上のSMTPサービスを使用してメッセージを送信します。 スクリプトが実行されているコンピューターにSMTPサービスがインストールされていない場合は、この値を使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2"><span class="wintitle">レポート</span>が、SMTPサーバーからの応答を待ってから接続をタイムアウトするまでの時間です。 </td> 
  </tr> 
 </tbody> 
</table>

1. [!DNL NewUserEmail()]関数と[!DNL UpdateUserEmail()]関数の場合、次の変数を設定します。

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> この変数用。.. </th> 
      <th colname="col2" class="entry"> 入力する情報 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 送信元 </td> 
      <td colname="col2">確認電子メールの「送信者」ヘッダー行に表示するテキストです。 この値は、<span class="wintitle"> CC</span>の値と同じになります。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>（オプション）新規および変更されたユーザーアカウントに関するすべてのメッセージのコピーを受け取る必要がある人またはエイリアスの有効な電子メールアドレス。 複数の電子メールアドレスを指定する場合は、アドレスをコンマで区切ります（スペースは使用できません）。 </p> <p>次に例を示します。<span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>注意： 受信者は、ユーザーパスワードを含む電子メールのコピーを受け取ります。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 件名 </td> 
      <td colname="col2"> 確認電子メールの件名ヘッダー行に表示するテキストです。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>ポータルへの実際のパス。 </p> <p>次に例を示します。<span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 本文 </td> 
      <td colname="col2"> <p>自動生成された電子メールに含まれるテキスト。 </p> <p>例えば、ログイン情報を提供するために送信される電子メールに含まれるデフォルトのテキストは次のようになります。 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Webポータルログイン情報は次のとおりです。 </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>UserName:username </p><p>新しいパスワード：password </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>次のURLを使用してポータルにアクセスできます。 </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">ポータルにログインした後、「<span class="wintitle">管理者</span>」タブでパスワードを変更できます。 </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. ファイルを保存して閉じます。
