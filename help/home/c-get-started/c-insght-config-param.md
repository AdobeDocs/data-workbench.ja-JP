---
description: Insight.cfg ファイル内でパラメーターを設定して、ネットワーク接続と Data Workbench の設定を指定します。
title: 設定パラメーター
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 70%

---

# 設定パラメーター{#configuration-parameters}

{{eol}}

Insight.cfg ファイル内でパラメーターを設定して、ネットワーク接続と Data Workbench の設定を指定します。

次の例には、[!DNL Insight.cfg] ファイルにデフォルトで含まれているパラメーターのみが示されています。

**新しいレイアウトビュー**

![](assets/config_tree_new_layout.png)

**元のレイアウトビュー**

![](assets/cfg_Workstation_AddServer.png)

新しい [!DNL Insight.cfg] お使いのバージョンのではファイルを使用できない可能性があります [!DNL Insight.cfg] ファイル。 これらのパラメーターの 1 つが必要な場合は、それを [!DNL Insight.cfg] 使用するファイル [!DNL Add Custom Key]をクリックし、パラメーターを右クリックして、名前とタイプを指定します。 また、 [!DNL .cfg] ファイル (Data Workbenchのインストールディレクトリにあります )。

パラメーターエントリを追加するためのモデルとして使用できる、[!DNL Insight.cfg] ファイルに使用可能なすべてのパラメーターの例を以下に示します。

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

以下の表に、使用可能な [!DNL Insight.cfg] ファイルのパラメーターに関する説明をアルファベット順に示します。

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Address </p> </td> 
   <td colname="col2"> <p>Data Workbench・サーバー・コンピュータのホスト名または数値 IP アドレス。 </p> <p>例：<span class="filepath">vsServer.mycompany.com または 192.168.1.90</span> </p> <p><span class="wintitle">Address</span> が指定されていない場合、Use Address File が false に設定されていれば、<span class="keyword">クライアント</span>は SSL Server Common Name パラメーターで指定された共通名を使用します。 </p> <p> <p>注意：Use Address File パラメーターが true に設定されている場合は、<span class="keyword">クライアント</span>で最初のプロファイルを開いてから、Address パラメーターに入力されたテキストを削除できます。その後、Network Location パラメーターの設定によって、クラスターのアドレスファイルのどの住所をマスターサーバーへの接続に使用するかが決定されます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Color Set </p> </td> 
   <td colname="col2"> <p><span class="keyword">クライアントアプリケーション</span>の背景色を指定します。選択肢は以下のとおりです。 </p> <p>0 = 黒 </p> <p>1 = 白 </p> <p>2 = モノクロ </p> <p>デフォルト値は 0（黒）です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Online Level </p> </td> 
   <td colname="col2"> <p>（オプション）。デフォルトでは、Data Workbenchを開くたびに、ストリーミング、オフライン、オンラインとしてインスタンスを動作させることができます。 選択肢は Streaming、Online、Offline です。デフォルトの設定では、Data Workbenchはオフラインで動作します。 </p> <p> <p>注意：デフォルトでオンラインで動作することを決定する前に、「 <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> オフラインおよびオンラインでの作業</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fonts </p> </td> 
   <td colname="col2"> <p>（オプション）。UTF8 ベースの unicode 特殊文字をレンダリングするために<span class="keyword">クライアント</span>が使用する必要があるフォントをリストしたベクトルです。リスト内のフォント数に制限はありません。 </p> <p>先頭のフォントは常に Lucida Sans Console でなければなりません。このパラメーターが <span class="filepath"> Insight.cfg</span> ファイル、Data Workbenchは、Lucida Sans コンソールのみを使用してテキストを表示します。 </p> <p> Data Workbenchは、リストの最初のフォントを使用して、レンダリングできない文字を検出するまで、すべての文字をレンダリングします。 レンダリングできない文字が出現した場合は、リストの 2 番目のフォントを使用してその文字をレンダリングします。そのData Workbenchが文字をレンダリングしない場合、フォントはリストの 3 番目のフォントを使用してその文字をレンダリングし、フォントリストの最後に到達するまで同様に続きます。 ベクトルに正しいフォントがリストされていない場合、Data Workbenchはその文字の 16 進値を表示します。 </p> <p> <p>注意：Data Workbenchの実行中は、このパラメーターを変更しないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Data Workbench表示のガンマ設定。 デフォルト値は 1.6 です。この値を変更することはお勧めしません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licensing </p> </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバー経由で Adobe License Server にアクセスしている場合のみ、Licensing ベクトルのパラメーターを変更する必要があります。 </p> <p><span class="keyword">クライアント</span>がプロキシサーバー経由で Adobe License Server にアクセスできるようにするパラメーターのセクション識別子です。Licensing ノードを展開して、以下のパラメーターを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Address </p> </td> 
   <td colname="col2"> <p>（オプション）。<span class="keyword">クライアント</span>が Adobe License Server にアクセスするために使用する必要があるプロキシサーバーのアドレス。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Port </p> </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバーのポート。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy User Name </p> </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバーのユーザー名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy Password </p> </td> 
   <td colname="col2"> <p>（オプション）。Proxy User Name に関連付けられたパスワード。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum Sample Size (MB) </p> </td> 
   <td colname="col2"> <p>1 台のコンピューター上で動作している<span class="keyword">クライアント</span>が使用するデータキャッシュ内で許容される最大サイズを指定します。 </p> <p>Sample Bytes パラメータが <span class="filepath"> Server.cfg</span> ファイルは、すべての <span class="keyword"> クライアント</span> Data Workbenchサーバー（デフォルトでは 250e6 バイト）に接続すると、Maximum Sample Size パラメーターを使用して、特定のコンピューターのデータキャッシュサイズをさらに制限できます。 このパラメーターは、ストレージまたは計算能力に制限のあるコンピューターにクライアントがインストールされている場合に役立ちます。 </p> <p> <p>注意：このパラメーターは、クライアントプログラムによってローカルにクエリーされるローカルデータサンプルのサイズを制限します。対照的に、<span class="filepath">cache.db</span> ファイルには、クライアントが接続する各プロファイル用のデータに加え、要素名とそのディメンションが含まれています。<span class="filepath">cache.db</span> ファイル内のこれらの要素名とディメンションは、ローカルクエリーの実行に必要です。そのため、データセット内の要素数を減らす以外にサイズを制限する方法はありません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名前 </p> </td> 
   <td colname="col2">（オプション）。<span class="keyword">クライアント</span>が<span class="keyword">サーバー</span>の識別に使用する名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Location </p> </td> 
   <td colname="col2"> <p>（オプション）。ネットワークの場所 <span class="keyword"> client</span> は、を使用してData Workbenchサーバーの共通名を IP アドレスに解決します。 使用可能なネットワーク位置は、サーバー上のアドレスファイルで定義されています。詳しくは、『サーバー製品のインストールと管理ガイド<i></i>』を参照してください。 </p> <p>ネットワーク位置を指定しない場合、<span class="keyword">クライアント</span>はデフォルトのネットワーク位置「Insight」を使用して共通名を解決します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Port </p> </td> 
   <td colname="col2"> <p><span class="keyword">クライアント</span>が要求を送信するポート。このポート番号は、要求をリッスンしているData Workbenchサーバーのポートと一致する必要があります。 安全な接続を行うため、通常は 443 を設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>プロキシアドレス </p> </td> 
   <td colname="col2"> <p>Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合は、少なくともこのパラメーターと Proxy Port パラメーターを入力する必要があります。 オプションで、Proxy User Name パラメーターと Proxy User Password パラメーターにも入力できます。 </p> <p>プロキシサーバーのアドレスです。 <span class="keyword"> クライアント</span> は、を使用してData Workbench・サーバにアクセスします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>プロキシパスワード </p> </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバーへのパスワード。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>プロキシポート </p> </td> 
   <td colname="col2"> <p>プロキシサーバーのポート。デフォルト値は 8080 です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>プロキシユーザー名 </p> </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバーのユーザー名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>検索 </p> </td> 
   <td colname="col2"> <p><span class="filepath">Insight.cfg</span> ファイル（または任意の <span class="filepath">.cfg</span> ファイル）内で、キー名、キータイプまたは値で検索してすばやくエントリを見つけることができます。ネストされた情報を探すため、大きなファイルを展開してスクロールする必要がなくなります。ディメンション名、サーバー名などを探せます。 </p> <p>データを探すには、このフィールドに検索フレーズを入力します。一致が見つかったかどうかによって、フィールドの色が変化します。一致はハイライト表示され、不一致は暗く表示されます。一致がない場合は、検索フィールドの背景が赤くなります。Enter キーを押すと、設定ツリーの一致があるすべての箇所が展開され、一致がない箇所は折りたたまれます。 </p> <p>「<span class="wintitle">検索</span>」フィールドでは正規表現も使用できます。例えば、"zip." という語を含むエントリを探すために、re: <span class="filepath">*zip.*</span> という正規表現を使用できます。 </p> <p>検索をクリアするには、<span class="uicontrol">Escape</span> キーを押します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>サーバー </p> </td> 
   <td colname="col2"> <p><span class="keyword">クライアント</span>から<span class="keyword">サーバー</span>への接続のベクトル見出し。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Client Certificate </p> </td> 
   <td colname="col2"> <p>複数の証明書がある場合を除いてオプションです。このData Workbenchのコピーの電子証明書を含むファイルの名前。 「デジタル証明書のダウンロードとインストール」でダウンロードしたファイルです。 </p> <p>例：<span class="filepath">Samantha Smith.pem</span> </p> <p>このパラメーターを空白のままにした場合、<span class="keyword">クライアント</span>は存在する証明書であれば何でも使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Server Common Name </p> </td> 
   <td colname="col2"> <p>Data Workbenchサーバーの共通名（電子証明書に割り当てられているもの）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Toolbar Icons </p> </td> 
   <td colname="col2"> <p>false に設定した場合、ワークステーションのユーザーインターフェイスにアイコンが表示されなくなり、ツールバーにテキストが表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use Address File </p> </td> 
   <td colname="col2"> <p>アドレスファイル内の設定が Address パラメーターの設定に優先するかどうかを指定します。選択肢は true または false です。true に設定した場合、アドレスファイルに設定が存在すれば、Address パラメーターの設定に優先します。デフォルト値は true です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use SSL </p> </td> 
   <td colname="col2">SSL を使用してサーバーとの間の安全な通信をData Workbenchするかどうかを指定します <span class="keyword"> クライアント</span>. 選択肢は true または false です。デフォルト値は true です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unhide All </p> </td> 
   <td colname="col2"> <p>（オプション）。以下の機能のいずれかを使用して非表示にしているすべての指標、ディメンション、フィルターを一時的に再表示できます。 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A"><span class="filepath">order.txt</span> ファイル内の [Exclusive] 設定 </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306"><span class="filepath">order.txt</span> ファイル内の Hide オプション </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8"><span class="filepath">.metric</span> ファイル、<span class="filepath">.dim</span> ファイル、<span class="filepath">.filter</span> ファイル内の Show パラメーター </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC"><span class="filepath">Transformation.cfg</span> ファイル内の Hidden パラメーター </li> 
     </ul> </p> <p>これらのメソッドについて詳しくは、 <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> メニュー項目を非表示にする</a>. </p> <p>選択肢は true または false です。デフォルト設定は false です。このパラメーターを true に変更すると、非表示の指標、ディメンション、フィルターが一時的に再表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unlock </p> </td> 
   <td colname="col2"> <p>（オプション）。ロックされているワークスペースのロック解除を許可するかどうかを指定します。選択肢は true と false です。true に設定するとロックされているワークスペースをロック解除でき、false に設定するとロック解除できません。デフォルト値は false です。ロックされているワークスペースについて詳しくは、「 <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> ワークスペースのロック解除</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Update Software </p> </td> 
   <td colname="col2"> <p>（オプション）。これを許可するかどうかを指定します <span class="keyword"> の </span>クライアントソフトウェアを更新し、Data Workbench・サーバで更新します。 選択肢は true または false です。デフォルト値は true です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User Folder </p> </td> 
   <td colname="col2"> <p>（オプション）。任意のワークスペース、指標、ディメンションまたは各プロファイルの設定ファイルのローカルコピーを格納するフォルダーの名前と場所を指定します。デフォルト設定は User\\で、インストールディレクトリ内の UserData Workbenchを指定します。 </p> <p>2 人のユーザーが同じコンピューターを共有している場合、この設定を変更すると役に立ちます。両方のユーザーを受け入れるため、どちらのユーザーもアクセス権を持つ共有フォルダーを指定できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
