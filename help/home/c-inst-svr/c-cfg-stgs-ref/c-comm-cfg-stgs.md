---
description: Insightサーバーまたはリピーター用の通信を設定する手順です。
solution: Insight
title: 通信の構成設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 通信の構成設定{#communications-configuration-settings}

Insightサーバーまたはリピーター用の通信を設定する手順です。

次のファイルのパラメーターを設定します。

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>この表に記載されていないパラメーターを変更する前に、アドビにお問い合わせください。

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> アクセス制御ファイル </td> 
   <td colname="col2"> <p>Access Control.cfgフ <span class="filepath"> ァイルの場 </span> 所。 デフォルトの場所は、 <span class="filepath"> Insight Serverまたは </span> Repeaterのインストー <span class="keyword"> ルディレクトリ内の </span> Access Control <span class="wintitle"> フォル </span> ダーです。 </p> <p>例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログディレクトリ </td> 
   <td colname="col2"> <p>監査ログをマップするフォルダ。 </p> <p>例： <filepath></filepath> </p> <p> <p>注意： 監査ログを別のローカルドライブにマップできます(例： <span class="filepath"> 文字列：P:\\Audit\\ </span>)を参照しますが、監査ログをネットワークドライブにマップしません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログの詳細 </td> 
   <td colname="col2"> このパラメーターは、trueまたはfalseに設定できます。 監査ログのフィルタリングを有効または無効にするために使用します。 すべてのリクエストが確実にログに記録されるようにするには、パラメーターをTrueに設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IPインターフェイス </td> 
   <td colname="col2"> <p>2つの異なるネットワークにアクセスするために2つのネットワークカードが使用可能な場合に使用するIPアドレス。 </p> <p>例：I <filepath></filepath><i>&lt; <span class="filepath"> IP アドレス </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Insightサーバーまたはリピーターがリスンする、安全で <span class="keyword"> ない(HTTP) </span> ポ <span class="wintitle"> ート </span> です。 デフォルトポートは 80 です。値を0に設定すると、安全でない接続が無効になります。 </p> <p>例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL暗号 </td> 
   <td colname="col2"> 一部の環境では、他の環境よりも強力な通信セキュリティが必要です。 特定のSSL暗号を使用する場合は、このパラメーターを使用して指定できます。 <p>例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSLポート </td> 
   <td colname="col2"> <p>Insightサーバーまたはリピーターがリスンする安全な(SSL <span class="keyword"> 経由の) </span> ポ <span class="wintitle"> ート </span> です。 デフォルトポートは 443 です。値を0に設定すると、セキュリティで保護された接続が無効になります。 </p> <p>例：<span class="filepath"></span> </p> <filepath></filepath> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> ログサーバー設定の見出しです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顧客名 </td> 
   <td colname="col2"> <p>次の例のように、管理アラートで「未指定」の顧客に対して表示される顧客名。 </p> <p>"15で顧客'未指定'のデータがセンサーXYZから受信されませんでした。" </p> <p>例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>上記の例を使用して、「未指定」の顧客に対する管理アラートは、次のように表示されるようになりました。 </p> <p>"15に顧客「CompanyAB」のデータをセンサーXYZから受信しません。" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string:ログ\\ </p> </td> 
   <td colname="col2"> <p>ログファイルを保存するフォルダーです。 </p> <p>例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>サーバーファイルマネージャーからこのフォルダーにアクセスするには、このパラメーターで指定する場所が、 <span class="wintitle"> Log Processing.cfgファイルのLog Pathsパラメーターで指定する場所と一致している必要があり </span><span class="filepath"></span> ます。 Log Processing.cfgファイル内のLogsディレクトリの変更について詳しくは、『データセット設定ガイド』の「ログ処理設定フ <span class="filepath"> ァイル」という章を参照 </span> してください <i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string:監査\\ </p> </td> 
   <td colname="col2"> <p>監査ログをマップするフォルダ。 </p> <p>例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注釈:  <p>監査ログを別のローカルドライブにマップできます(例： <span class="filepath"> 文字列：P:\\Audit\\ </span>)を参照しますが、監査ログをネットワークドライブにマップしません。 </p> <p>サーバーファイルマネージャーからこのフォルダーにアクセスするには、このパラメーターで指定され <span class="wintitle"></span>た場所が、このファイルのAccess Log Directoryパラメーターで指定した場所と一致している必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insightサーバーにのみ適用されま </span>す。 </p> <p>Insightサーバークラスターに中央の正規化サーバーを指定する方法について詳しくは、『デー <span class="keyword"> タセット設 </span> 定ガイド』の「ログ処理の設定ファイル」という章を <i>参照してください</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string:/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insightサーバーにのみ適用されま </span>す。 </p> <p><span class="keyword"> Insight Serverの詳細なステータスイン </span> ターフェイスでレ <span class="keyword"> ポートのステータスを表示できるように </span>します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

