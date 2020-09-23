---
description: Insightサーバーまたはリピーター用の通信を設定する手順です。
solution: Analytics
title: 通信の設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---


# 通信の設定{#communications-configuration-settings}

Insightサーバーまたはリピーター用の通信を設定する手順です。

次のファイルのパラメーターを設定します。

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>この表に記載されていないパラメーターを変更する前に、Adobeにお問い合わせください。

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
   <td colname="col2"> <p>アクセス制御 <span class="filepath"> .cfg </span> ファイルの場所。 デフォルトの場所は、 <span class="filepath"> Insightサーバー </span> または <span class="keyword"> リピーターのインストールディレクトリ内のアクセス制御 </span><span class="wintitle"></span> フォルダーです。 </p> <p>例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログディレクトリ </td> 
   <td colname="col2"> <p>監査ログのマップ先フォルダー。 </p> <p>例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意： 監査ログを別のローカルドライブにマップできます(例： <span class="filepath"> string:P:\\Audit\\ </span>)。ただし、監査ログをネットワークドライブにマップしないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログの詳細 </td> 
   <td colname="col2"> このパラメーターはtrueまたはfalseに設定できます。 監査ログのフィルタリングを有効または無効にするために使用します。 すべてのリクエストが確実にログに記録されるようにするには、このパラメーターをTrueに設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IPインターフェイス </td> 
   <td colname="col2"> <p>2つの異なるネットワークにアクセスするために2つのネットワークカードが使用可能な場合に使用するIPアドレス。 </p> <p>例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Insightサーバー <span class="keyword"> または </span> リピーターがリスンする、安全でない(HTTP)ポート <span class="wintitle"></span> 。 デフォルトポートは 80 です。値0を入力すると、セキュリティで保護されていない接続が無効になります。 </p> <p>例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL暗号 </td> 
   <td colname="col2"> 一部の環境は、他のユーザーよりも強い通信セキュリティを必要とします。 特定のSSL暗号スイートを使用する場合は、このパラメーターを使用して指定できます。 <p>例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSLポート </td> 
   <td colname="col2"> <p>Insightサーバー <span class="keyword"> または </span> リピーターがリスンする安全な（SSL経由の）ポート <span class="wintitle"></span> 。 デフォルトポートは 443 です。値0を入力すると、セキュリティで保護された接続が無効になります。 </p> <p>例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Logging Server設定の見出しです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顧客名 </td> 
   <td colname="col2"> <p>次の例のように、管理アラートで「未指定」の顧客に表示される顧客名。 </p> <p>"センサーXYZから顧客'未指定'のデータを15で受信しませんでした。" </p> <p>例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>上の例で、「未指定」のお客様に対する管理アラートは、次のように表示されるようになりました。 </p> <p>"センサーXYZから顧客「CompanyAB」のデータを15で受信しませんでした。" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string:ログ\\ </p> </td> 
   <td colname="col2"> <p>ログファイルを格納するフォルダー。 </p> <p>例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>サー <span class="wintitle"> バーファイルマネージャーからこのフォルダーにアクセスするには、このパラメーターで指定する場所 </span>が、Log Processing.cfgファイルのLog Pathsパラメーターで指定する場所と一致している必要があり <span class="filepath"></span> ます。 Log Processing.cfgファイル内のLogsディレクトリの変更について詳しくは、『デー <span class="filepath"> タセット設定ガイド </span> 』の「ログ処理設定ファイル」という章を参照してください <i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string:監査\\ </p> </td> 
   <td colname="col2"> <p>監査ログのマップ先フォルダー。 </p> <p>例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注釈:  <p>監査ログを別のローカルドライブにマップできます(例： <span class="filepath"> string:P:\\Audit\\ </span>)。ただし、監査ログをネットワークドライブにマップしないでください。 </p> <p>サーバーファイルマネージャーからこのフォルダーにアクセスするには、この <span class="wintitle"> パラメーターで指定する場所 </span>が、このファイルのAccess Log Directoryパラメーターで指定する場所と一致している必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insightサーバーにのみ適用され </span>ます。 </p> <p>Insightサーバークラスターに対して中央の正規化サーバーを指定する方法について詳しくは、『デー <span class="keyword"> タセット設定ガイド </span><i></i>』の「ログ処理設定ファイル」という章を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string:/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insightサーバーにのみ適用され </span>ます。 </p> <p><span class="keyword"> Insightサーバーの詳細なステータスインターフェイスで、 </span> レポートのステータスを表示でき <span class="keyword"></span>ます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
