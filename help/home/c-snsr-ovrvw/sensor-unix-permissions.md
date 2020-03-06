---
description: コレクタ・モジュール、送信機プロセス、構成ファイルなど、Sensor UNIXファイルの権限に関する情報。
title: Sensor UNIXファイルの権限
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sensor UNIXファイルの権限{#sensor-unix-file-permissions}

コレクタ・モジュール、送信機プロセス、構成ファイルなど、Sensor UNIXファイルの権限に関する情報。

## コレクタモジュール {#section-49c855baece24c4695184bfcbeeddebf}

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
   <td colname="col2"> <p>mod_visual_sciences.so（Apache WebサーバーおよびIBM HTTPサーバー上） </p> <p>libvisual_sciences.soおよびJ2EECollector.jar（J2EEアプリケーションサーバー上） </p> <p>aol_visual_sciences.so（AOL Webサーバー上） </p> <p>saf_visual_sciences.so （Sun Java Webサーバー上） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>デフォルトの権限 </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x（IBM HTTPおよびApache 1.3.x） </p> <p>rwx rwx r-x(Apache 2.0.x) </p> <p>rwx —x —x （J2EE、AOL、Sun Java Webサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>閲覧者 </p> </td> 
   <td colname="col2"> <p>Webサーバー。ルートユーザーとして実行される場合もありますが、特定のユーザーアカウントで実行される場合が多くなります。 </p> <p>Webサーバーがルート以外のアカウントで実行される場合は、このファイルの権限によって、そのアカウントで読み取りを許可する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>実行形式 </p> </td> 
   <td colname="col2"> <p>Webサーバーの子プロセス </p> <p>子プロセスは、Webサーバー設定で指定されたユーザーアカウントで実行されます。 多くのサーバでは、これは「nobody」と呼ばれる非常に限られた権限を持つ特別なアカウントです。 ただし、このアカウントを使用しないWebサーバーもあります。 Webサーバーの設定ファイルを確認し、設定するユーザーアカウントを決定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>読み取り元 </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>diskQueueファイル </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 書き込み先 </td> 
   <td colname="col2"> diskQueueファイル </td> 
  </tr> 
 </tbody> 
</table>

## 送信機プロセス {#section-8af432472e9d4bd9a42270bf27adf33a}

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
   <td colname="col2"> <p>rw- r— r— （IBM HTTP、AOL、およびSun Java Webサーバ） </p> <p>rw-rw- r— （Apache WebサーバーおよびJ2EEアプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閲覧者 </td> 
   <td colname="col2"> 送信プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> -- </td> 
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
   <td colname="col2"> <p>rw- r— r— （IBM HTTP、AOL、およびSun Java Webサーバ） </p> <p>rw-rw- r— （Apache WebサーバーおよびJ2EEアプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閲覧者 </td> 
   <td colname="col2"> <p>コレクタモジュール </p> <p>送信プログラム </p> <p>Sensorのインストール、設定、および管理を担当する管理者 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> Sensorのインストール、設定、および管理を担当する管理者 </td> 
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
   <td colname="col2"> <p>rw- r— r— （IBM HTTP、AOL、およびSun Java Webサーバ） </p> <p>rw-rw- r— （Apache WebサーバーおよびJ2EEアプリケーションサーバー） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 閲覧者 </td> 
   <td colname="col2"> 送信プログラム </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作成者 </td> 
   <td colname="col2"> -- </td> 
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
   <td colname="col1"> File name </td> 
   <td colname="col2"> ユーザー定義 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> デフォルトの権限 </td> 
   <td colname="col2"> rw- rw- rw- （すべてのサーバタイプ） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>閲覧者 </p> </td> 
   <td colname="col2"> <p>コレクタモジュール </p> <p>送信プログラム </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>作成者 </p> </td> 
   <td colname="col2"> <p>コレクタモジュール </p> <p>送信プログラム </p> </td> 
  </tr> 
 </tbody> 
</table>

