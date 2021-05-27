---
description: Insightサーバーまたはリピーター用の通信を設定する手順です。
title: 通信の設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 通信の設定{#communications-configuration-settings}

Insightサーバーまたはリピーター用の通信を設定する手順です。

次のファイルのパラメーターを入力します。

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>この表に記載されていないパラメータを変更する前に、Adobeにお問い合わせください。

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
   <td colname="col2"> <p><span class="filepath"> Access Control.cfg </span>ファイルの場所。 デフォルトの場所は、 <span class="keyword"> Insightサーバー</span>または<span class="wintitle">リピーター</span>のインストールディレクトリ内の<span class="filepath">アクセス制御</span>フォルダーです。 </p> <p>例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログディレクトリ </td> 
   <td colname="col2"> <p>監査ログのマッピング先のフォルダー。 </p> <p>例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意： 監査ログを別のローカルドライブにマッピングできます(例：<span class="filepath">文字列：P:\\Audit\\ </span>)ですが、監査ログをネットワークドライブにマッピングしないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログの詳細 </td> 
   <td colname="col2"> このパラメーターはtrueまたはfalseに設定できます。 監査ログのフィルタリングを有効または無効にするために使用されます。 すべてのリクエストがログに記録されるようにするには、パラメーターをTrueに設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IPインターフェイス </td> 
   <td colname="col2"> <p>2つの異なるネットワークにアクセスするために2つのネットワークカードを使用できる場合に使用するIPアドレス。 </p> <p>例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバー</span>または<span class="wintitle">リピーター</span>がリッスンする、セキュアでない(HTTP)ポート。 デフォルトポートは 80 です。値0を入力すると、セキュリティで保護されていない接続が無効になります。 </p> <p>例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL暗号 </td> 
   <td colname="col2"> 一部の環境では、他の環境よりも強力な通信セキュリティが必要です。 特定のSSL暗号を使用する場合は、このパラメーターを使用して指定できます。 <p>例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSLポート </td> 
   <td colname="col2"> <p><span class="keyword"> Insightサーバー</span>または<span class="wintitle">リピーター</span>がリッスンするセキュアな（SSLを介した）ポート。 デフォルトポートは 443 です。値0を入力すると、セキュリティで保護された接続が無効になります。 </p> <p>例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> ログサーバー設定の見出しです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> お客様名 </td> 
   <td colname="col2"> <p>次の例のように、管理アラートの「未指定」の顧客に表示される顧客名。 </p> <p>「15に、顧客「未指定」のセンサーXYZからデータを受信していません。」 </p> <p>例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>上記の例を使用すると、「未指定」のお客様に対する管理アラートは次のようになります。 </p> <p>「15の顧客'CompanyAB'のセンサーXYZからデータを受け取っていません。」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> ローカルパス=文字列：ログ\\ </p> </td> 
   <td colname="col2"> <p>ログファイルを格納するフォルダー。 </p> <p>例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p><span class="wintitle">サーバーファイルマネージャー</span>からこのフォルダーにアクセスするには、このパラメーターで指定する場所が、<span class="filepath"> Log Processing.cfg </span>ファイルのLog Pathsパラメーターで指定する場所と一致する必要があります。 <span class="filepath"> Log Processing.cfg </span>ファイルのLogsディレクトリの変更について詳しくは、『<i>データセット設定ガイド</i>』の「ログ処理設定ファイル」の章を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> ローカルパス=文字列：監査\\ </p> </td> 
   <td colname="col2"> <p>監査ログのマッピング先のフォルダー。 </p> <p>例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注釈:  <p>監査ログを別のローカルドライブにマッピングできます(例：<span class="filepath">文字列：P:\\Audit\\ </span>)ですが、監査ログをネットワークドライブにマッピングしないでください。 </p> <p><span class="wintitle">サーバーファイルマネージャー</span>からこのフォルダーにアクセスするには、このパラメーターで指定する場所が、このファイルのAccess Log Directoryパラメーターで指定する場所と一致する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>このパラメーターは、<span class="keyword"> Insightサーバー</span>にのみ適用されます。 </p> <p><span class="keyword"> Insightサーバー</span>クラスターに対して中央の正規化サーバーを指定する方法について詳しくは、『<i>データセット設定ガイド</i>』の「ログ処理設定ファイル」の章を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string:/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>このパラメーターは、<span class="keyword"> Insightサーバー</span>にのみ適用されます。 </p> <p><span class="keyword"> Insightサーバー</span>の詳細ステータスインターフェイスに<span class="keyword">レポートの</span>ステータスを表示できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
