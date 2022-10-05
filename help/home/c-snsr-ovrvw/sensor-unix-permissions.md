---
description: Sensor UNIX ファイルの権限に関する情報（コレクターモジュール、トランスミッタープロセス、設定ファイルなど）。
title: センサーの UNIX ファイルの権限
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
exl-id: 07cbc7df-c628-437d-9ca1-b006da8de242
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 6%

---

# センサーの UNIX ファイルの権限{#sensor-unix-file-permissions}

{{eol}}

Sensor UNIX ファイルの権限に関する情報（コレクターモジュール、トランスミッタープロセス、設定ファイルなど）。

## コレクターモジュール {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 画質 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ファイル名 </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so(Apache Web サーバーおよびIBM HTTP サーバー上 ) </p> <p>libvisual_sciences.so と J2EECollector.jar（J2EE アプリケーションサーバー上） </p> <p>aol_visual_sciences.so （AOL Web サーバー上） </p> <p>saf_visual_sciences.so（Sun Java Web サーバー上） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの権限 </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP および Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx —x —x （J2EE、AOL、Sun Java Web サーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>読み取り担当者 </p> </td> 
   <td colname="col2"> <p>Web サーバー。ルートユーザーとして実行される場合もありますが、特定のユーザーアカウントで実行される場合も多くあります。 </p> <p>Web サーバーが root 以外のアカウントで実行されている場合は、このファイルに対する権限により、そのアカウントがファイルを読み取ることが許可されている必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実行形式 </p> </td> 
   <td colname="col2"> <p>Web サーバーの子プロセス </p> <p>子プロセスは、Web サーバー設定で指定されたユーザーアカウントで実行されます。 多くのサーバーでは、これは「nobody」と呼ばれる特別な権限を持つ特別なアカウントですが、すべての Web サーバーがこのアカウントを使用するわけではありません。 Web サーバーの設定ファイルを調べて、設定されているユーザーアカウントを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>読み取り元 </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>diskQueue ファイル </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 書き込み先 </td> 
   <td colname="col2"> diskQueue ファイル </td> 
  </tr> 
 </tbody> 
</table>

## トランスミッタープロセス {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 画質 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ファイル名 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの権限 </p> </td> 
   <td colname="col2"> <p>rw- r- r- (IBM HTTP、AOL、Sun Java Web サーバ ) </p> <p>rw- rw- r:（Apache Web サーバーと J2EE アプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 読み取り担当者 </td> 
   <td colname="col2"> 送信機プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## 設定ファイル {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 画質 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ファイル名 </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの権限 </p> </td> 
   <td colname="col2"> <p>rw- r- r- (IBM HTTP、AOL、Sun Java Web サーバ ) </p> <p>rw- rw- r:（Apache Web サーバーと J2EE アプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 読み取り担当者 </td> 
   <td colname="col2"> <p>コレクターモジュール </p> <p>送信機プログラム </p> <p>Sensor のインストール、設定、保守を担当する管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> Sensor のインストール、設定、保守を担当する管理者 </td> 
  </tr> 
 </tbody> 
</table>

## 認証局ファイル {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 画質 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ファイル名 </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの権限 </p> </td> 
   <td colname="col2"> <p>rw- r- r- (IBM HTTP、AOL、Sun Java Web サーバ ) </p> <p>rw- rw- r:（Apache Web サーバーと J2EE アプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 読み取り担当者 </td> 
   <td colname="col2"> 送信機プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> — </td> 
  </tr> 
 </tbody> 
</table>

## ディスクキュー {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 画質 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ファイル名 </td> 
   <td colname="col2"> ユーザー定義 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> デフォルトの権限 </td> 
   <td colname="col2"> rw- rw- rw- （すべてのサーバタイプ） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>読み取り担当者 </p> </td> 
   <td colname="col2"> <p>コレクターモジュール </p> <p>送信機プログラム </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>作成者 </p> </td> 
   <td colname="col2"> <p>コレクターモジュール </p> <p>送信機プログラム </p> </td> 
  </tr> 
 </tbody> 
</table>
