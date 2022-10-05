---
description: Report Portal 内でのへのアクセス権と権限は、個々のユーザーアカウントとグループアカウントを使用して制御します。
title: Email.asp ファイルの編集
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 5%

---

# Email.asp ファイルの編集{#edit-the-email-asp-file}

{{eol}}

Report Portal 内でのへのアクセス権と権限は、個々のユーザーアカウントとグループアカウントを使用して制御します。

新しいアカウントを追加したり、既存のアカウントを編集したりするたびに、そのアカウントに対して指定した電子メールアドレスに確認の電子メールを送信できます ( [アカウントの操作](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)) をコピーして、 [!DNL email.asp] ファイル。

>[!NOTE]
>
>通知電子メールは、アカウントの電子メールアドレスを指定し、 [!DNL email.asp] ファイル。 あるアカウントに関する通知 E メールを送信しない場合は、アカウントの E メールフィールドを空白のままにします。

このファイルは、 `\*PortalName*\PortalASP` フォルダー。

1. IIS が実行されているマシンで、 [!DNL email.asp] ファイルをメモ帳などのテキストエディターで作成します。
1. 次の変数を設定します。

<table id="table_44F52DA266364DF993C40678A28E0F0D">
 <thead>
  <tr>
   <th colname="col1" class="entry"> この変数の場合。.. </th>
   <th colname="col2" class="entry"> 入力する情報 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> smtpserver </td>
   <td colname="col2"> <p>メッセージの送信に使用する SMTP サーバーの DNS 名または IP アドレス。 </p> <p>例： <span class="filepath"> mail.hq.omniture.com</span></p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpserverport </td>
   <td colname="col2"> SMTP サーバーが接続をリッスンするポートです。 これは通常、ポート 25 です。 </td>
  </tr>
  <tr>
   <td colname="col1"> sendusing </td>
   <td colname="col2"> <p>メッセージの送信方法を示します。 値は以下のとおりです。 </p> <p>1 — ローカルにインストールされた SMTP サービスを使用してメッセージを送信します。 スクリプトが実行されているコンピューターに SMTP サービスがインストールされている場合は、この値を使用します。 </p> <p>2 — ネットワーク上の SMTP サービスを使用してメッセージを送信します。 スクリプトが実行されているコンピューターに SMTP サービスがインストールされていない場合は、この値を使用します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> smtpconnectiontimeout </td>
   <td colname="col2">時間 <span class="wintitle"> レポート</span> は、SMTP サーバーからの応答が待ってから、接続がタイムアウトする必要があります。 </td>
  </tr>
 </tbody>
</table>

1. の [!DNL NewUserEmail()] および [!DNL UpdateUserEmail()] 関数では、次の変数を設定します。

   <table id="table_91C5E36B84A94C4097EE5993592BE587">
   <thead>
   <tr>
      <th colname="col1" class="entry"> この変数の場合。.. </th>
      <th colname="col2" class="entry"> 入力する情報 </th>
   </tr>
   </thead>
   <tbody>
   <tr>
      <td colname="col1"> 送信元 </td>
      <td colname="col2">確認 E メールの「開始」ヘッダー行に表示するテキストです。 この値は <span class="wintitle"> CC</span> の値です。 </td>
   </tr>
   <tr>
      <td colname="col1"> CC </td>
      <td colname="col2"> <p>（オプション）。新規および変更されたユーザーアカウントに関するすべてのメッセージのコピーを受け取る人またはエイリアスの有効な電子メールアドレス。 複数の電子メールアドレスを指定するには、複数の電子メールアドレスをコンマで区切ります（スペースは使用できません）。 </p> <p>例： <span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>注意：受信者には、ユーザーのパスワードが記載された電子メールのコピーが届きます。 </p> </p> </td>
   </tr>
   <tr>
      <td colname="col1"> 件名 </td>
      <td colname="col2"> 確認 E メールの件名ヘッダー行に表示するテキストです。 </td>
   </tr>
   <tr>
      <td colname="col1"> WebPath </td>
      <td colname="col2"> <p>ポータルへの実際のパス。 </p> <p>例： <span class="filepath"> https://portal.omniture.com/Example</span></p> </td>
   </tr>
   <tr>
      <td colname="col1"> 本文 </td>
      <td colname="col2"> <p>自動生成された E メールに含まれるテキスト。 </p> <p>例えば、ログイン情報を提供するために送信される電子メールに含まれるデフォルトのテキストは次のとおりです。
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">Web ポータルのログイン情報は次のとおりです。 </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>ユーザー名：ユーザー名 </p><p>新しいパスワード：パスワード </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>次の URL を使用してポータルにアクセスできます。 </p><p><span class="filepath"> https://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">ポータルにログインした後、 <span class="wintitle"> 管理者</span> タブをクリックします。 </li>
      </ul></p> </td>
   </tr>
   </tbody>
   </table>

1. ファイルを保存して閉じます。
