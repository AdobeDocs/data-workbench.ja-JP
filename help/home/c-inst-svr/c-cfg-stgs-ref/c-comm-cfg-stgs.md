---
description: Insight サーバーまたはリピーター用の通信を設定する手順です。
title: 通信の設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 通信の設定{#communications-configuration-settings}

{{eol}}

Insight サーバーまたはリピーター用の通信を設定する手順です。

次のファイルにあるパラメーターを入力します。

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
   <td colname="col2"> <p>の場所 <span class="filepath"> Access Control.cfg </span> ファイル。 デフォルトの場所は、 <span class="filepath"> アクセス制御 </span> フォルダー内の <span class="keyword"> Insight サーバー </span> または <span class="wintitle"> リピーター </span> インストールディレクトリ。 </p> <p>例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログディレクトリ </td> 
   <td colname="col2"> <p>監査ログをマッピングするフォルダーです。 </p> <p>例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意：監査ログを別のローカルドライブにマッピングできます ( 例： <span class="filepath"> 文字列：P:\\Audit\\ </span>) ですが、監査ログをネットワークドライブにマッピングしないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクセスログの詳細 </td> 
   <td colname="col2"> このパラメーターは true または false に設定できます。 監査ログのフィルタリングを有効または無効にするために使用します。 すべてのリクエストが確実にログに記録されるようにするには、パラメーターを True に設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP インターフェイス </td> 
   <td colname="col2"> <p>2 つの異なるネットワークにアクセスするために 2 つのネットワークカードを使用できる場合に使用する IP アドレス。 </p> <p>例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>非セキュア (HTTP) ポート。 <span class="keyword"> Insight サーバー </span> または <span class="wintitle"> リピーター </span> リッスンします。 デフォルトポートは 80 です。値を 0 に入力すると、セキュリティで保護されていない接続が無効になります。 </p> <p>例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL 暗号 </td> 
   <td colname="col2"> 一部の環境では、他の環境よりも強力な通信セキュリティが必要です。 特定の SSL 暗号を使用する場合は、このパラメーターで指定できます。 <p>例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL ポート </td> 
   <td colname="col2"> <p>（SSL 経由の）セキュアなポート。 <span class="keyword"> Insight サーバー </span> または <span class="wintitle"> リピーター </span> リッスンします。 デフォルトポートは 443 です。値 0 を入力すると、セキュア接続が無効になります。 </p> <p>例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> ログサーバー設定の見出しです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顧客名 </td> 
   <td colname="col2"> <p>次の例に示すように、管理アラートで「未指定」の顧客に表示される顧客名。 </p> <p>"15 のお客様「未指定」のセンサー XYZ からデータを受信していません。" </p> <p>例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>上記の例を使用して、未指定の顧客の管理アラートは次のようになりました。 </p> <p>「15 のお客様「CompanyAB」のセンサー XYZ からデータを受け取っていません。」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ファイルサーバー： </p> <p> ローカルパス=文字列：ログ\\ </p> </td> 
   <td colname="col2"> <p>ログファイルを保存するフォルダーです。 </p> <p>例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>このフォルダーに <span class="wintitle"> サーバーファイルマネージャー </span>に設定する場合、このパラメーターで指定する場所は、 <span class="filepath"> Log Processing.cfg </span> ファイル。 Logs ディレクトリの変更の詳細については、 <span class="filepath"> Log Processing.cfg </span> ファイルについては、 <i>データセット設定ガイド</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ファイルサーバー： </p> <p> ローカルパス=文字列：監査\\ </p> </td> 
   <td colname="col2"> <p>監査ログをマッピングするフォルダーです。 </p> <p>例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注釈:  <p>監査ログを別のローカルドライブにマッピングできます ( 例： <span class="filepath"> 文字列：P:\\Audit\\ </span>) ですが、監査ログをネットワークドライブにマッピングしないでください。 </p> <p>このフォルダーに <span class="wintitle"> サーバーファイルマネージャー </span>の場合、このパラメーターで指定する場所は、このファイルの Access Log Directory パラメーターで指定した場所と一致する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insight サーバー </span>. </p> <p>中央の正規化サーバーを <span class="keyword"> Insight サーバー </span> クラスターについては、 <i>データセット設定ガイド</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string:/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>このパラメーターは、 <span class="keyword"> Insight サーバー </span>. </p> <p>表示可能 <span class="keyword"> レポートの </span> のステータス（詳細ステータスインターフェイス） <span class="keyword"> Insight サーバー </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
