---
description: Report Server.cfgパラメーターに関する情報です。
title: Report Server.cfg のパラメーター
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 8%

---

# Report Server.cfg のパラメーター{#report-server-cfg-parameters}

Report Server.cfgパラメーターに関する情報です。

[Insightサーバーへの接続の設定](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)に示すサンプル[!DNL Report Server.cfg]には、デフォルトで[!DNL Report Server.cfg]ファイルに含まれているパラメーターのみが含まれています。

プロキシサーバー経由でAdobeLicense Serverに連絡する場合は、Licensingベクトルとそのパラメーターを[!DNL Report Server.cfg]に追加する必要があります。 Licensingベクトルのモデルを使用できる、このベクトルとそのパラメーターの例を以下に示します。

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

次の表に、[!DNL Report Server.cfg]ファイルのパラメーターの説明を示します。

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel拡張機能 </td> 
   <td colname="col2"> <p>サポートされるExcelの拡張機能を次に示します。 </p> <p>Excel Extension = string:<span class="filepath"> .xlsx </span> </p> <p>Excel Extension = string:<span class="filepath"> .xls </span>（デフォルト） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts </td> 
   <td colname="col2"> <p>（オプション）<span class="keyword"> Report Server </span>がUTF8ベースのUnicode特殊文字をレンダリングする際に使用する必要があるフォントをリストしたベクトルです。 リスト内のフォント数に制限はありません。 </p> <p>先頭のフォントは常に Lucida Sans Console でなければなりません。このパラメーターが<span class="filepath"> Report Server.cfg </span>ファイルに含まれていない場合、<span class="keyword">レポートサーバー</span>はLucida Sans Consoleのみを使用してテキストを表示します。 </p> <p> <span class="keyword"> Report Serverでは、レンダリングできない文字が検出されるまで、リストの最初のフォントを </span> 使用してすべての文字がレンダリングされます。次に、リストの2番目のフォントを使用してその文字をレンダリングします。 そのフォントが文字をレンダリングしない場合、<span class="keyword"> Report Server </span>はリストの3番目のフォントを使用してその文字をレンダリングします。フォントリストの終わりに達するまで同様です。 ベクトルに正しいフォントがリストされていない場合、<span class="keyword">レポートサーバー</span>には、その文字の16進数値が表示されます。 </p> <p> <p>注意： <span class="keyword">レポートサーバー</span>の実行中は、このパラメーターに変更を加えないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle">  </span> .png <span class="filepath">  </span> ファイル出力のガンマ設定デフォルト値は 1.6 です。 </p> <p> <p>注意： Adobeでは、この値を変更することをお勧めしません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing </td> 
   <td colname="col2"> <p>（オプション）プロキシサーバー経由でAdobeのライセンスサーバーにアクセスする場合にのみ、このベクトルのパラメーターを変更する必要があります。 </p> <p>プロキシサーバーを介してAdobeのライセンスサーバーに接続するように設定したパラメーターのセクション識別子。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> <span class="keyword"> Report Server </span>がAdobeのライセンスサーバーにアクセスする際に使用する必要があるプロキシサーバーのアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> （オプション）<span class="wintitle">プロキシユーザー名</span>に関連付けられているパスワードです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> プロキシサーバーのポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> （オプション）プロキシサーバーへのアクセスに使用するユーザー名です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Network Location </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がサーバーの共通名をIPアドレスに解決するために使用するネットワークの場所。 ネットワークの場所は、Data WorkbenchサーバーコンピューターのAddressesディレクトリにあるアドレスファイルで定義されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバー </td> 
   <td colname="col2"> <p>レポートを生成するために接続する必要があるData Workbenchサーバーコンピューター<span class="keyword">レポートサーバー</span>を構成するために設定するパラメーターのセクション識別子。 このベクトルには、このベクトルに含まれる項目の数を示す数値が含まれます。 </p> <p>各サーバーに対して、serverInfoエントリを追加し、必要に応じてパラメーターを設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>が接続してレポートを生成する必要があるData WorkbenchサーバーコンピューターのIPアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がData Workbenchサーバーを識別するために内部的に使用する名前。 これは単に内部ラベルなので、任意の名前を使用できます。 一貫性を保つために、サーバーのデジタル証明書に記載されている共通名を使用することをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がData Workbenchサーバーと通信するポート。 安全な接続の場合、この値は通常443です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシアドレス </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がData Workbenchサーバーにアクセスする際に使用する必要があるプロキシサーバーのアドレス。 このパラメーターは、サーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> プロキシサーバーへのパスワード。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシポート </td> 
   <td colname="col2"> プロキシサーバーのポート。デフォルト値は 8080 です。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> プロキシサーバーのユーザー名です。 このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>コンピューターのSSL証明書ファイルの名前です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <span class="wintitle"> Data Workbenchサーバーのデジタル証明書 </span> に一覧表示されるサーバー共通名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> Data Workbenchサーバーと<span class="keyword">レポートサーバー</span>間の安全な通信にSSLが使用されるかどうかを示します。 選択肢は true または false です。デフォルト値は true です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果のメモリ制限(KB) </td> 
   <td colname="col2"> <p>レポートおよびアラートで使用可能にするメモリ量(KB)。 デフォルト値は 50000 です。 </p> <p>レポートの実行時に、<span class="keyword">レポートサーバー</span>が最初にこの値を確認し、次にMaximum Slice Sizeパラメーターの値を確認します。 例えば、このパラメーターを50,000に設定し、スライスの最大サイズを50に設定した場合、より多くのワークスペースを実行できる領域があっても、<span class="keyword">レポートサーバー</span>は一度に50個のワークスペースのみを実行します。 </p> <p> <p>注意： この制限は、Data Workbenchサーバーのクエリメモリ制限パラメーターに設定された値を超えないようにする必要があります。また、同時にレポートを実行する他のクエリに対して若干の余裕を持たせるために、<span class="wintitle">メモリ制限</span>より少し低く設定するのが理想的です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大スライスサイズ </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>が一度に実行できるレポートワークスペースの最大数です。 デフォルト値は 50 です。<span class="keyword">レポートサーバー</span>でこの設定を使用する方法について詳しくは、<span class="wintitle">結果メモリ制限(KB) </span>パラメーターの説明を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software </td> 
   <td colname="col2"> <p>この<span class="keyword">レポートサーバーの</span>ソフトウェアをData Workbenchサーバーによって更新させるかどうかを示します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>次に、モデルを使用できるこのパラメーターの例を示します。 </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGLハードウェアレンダリングを使用 </td> 
   <td colname="col2"> <p><span class="keyword">レポートサーバー</span>がハードウェアレンダリング（コンピューターのグラフィックカードなど）を使用してレポート出力を生成するかどうかを制御します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>このパラメーターは、グラフィックカードに問題が発生している場合にのみfalseに設定する必要があります。 falseに設定した場合、<span class="keyword">レポートサーバー</span>はハードウェアレンダリングを使用せず、デフォルトでソフトウェアレンダリングを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポート </td> 
   <td colname="col2"> レポートを設定するために設定するパラメーターのセクション識別子。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完了メッセージの間隔 </td> 
   <td colname="col2"> <p><span class="keyword">レポートサーバー</span>が、レポートまたはアラートの生成中にクエリが実行されているときに完了ステータスメッセージを印刷する頻度（秒）。 デフォルト値は 120 秒です。 </p> <p>例：Workspaceクエリが62.145672%完了した。 </p> <p>完了メッセージは<span class="filepath"> reportserver.log </span>に書き込まれ、サーバーと同期されます。 この設定は、各レポートセットに対して前後に送信される<span class="filepath"> status.txt </span>ファイルを制御するので、完了率がサムネールと共に表示されます。 レポートセットが完了するか、間隔に達する（いずれか早い方）たびに、メッセージが送信されます。 この値を大きく設定すると、クライアントインターフェイスでサムネールによって生成されたレポートの表示速度は低くなりますが、表示される中間メッセージの数は低くなります。 小さい値を指定すると、<span class="keyword"> status.txt </span>メッセージが変更されるたびに、<span class="filepath"> Report Server </span>サーバーからプロファイルへ、すべてのDPUと接続されているすべてのクライアントへデータが同期されるので、データの同期に大きな時間がかかる場合があります。 </span></p> <p>この設定パラメーターの設定に関係なく、レポートセットが完了すると、システムは常に<span class="filepath"> status.txt </span>ファイルを送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>このベクトルに含まれる項目の数を示す数値です。 レポートを作成するプロファイルごとに、プロファイルベクトルに<span class="wintitle"> ReportProfile </span>エントリを追加し、Serverパラメーターとプロファイルパラメーターを設定します。 </p> <p> <span class="wintitle"> サーバー </span> -  <span class="keyword"> Report ServerがData Workbenchサーバーを識別する際に内部的に </span> 使用する名前。この名前は、Data WorkbenchサーバーのSSL証明書に一覧表示されるサーバー共通名である必要があります。 </p> <p> <span class="wintitle"> プロファイル </span>  — レポートを作成するプロファイルの名前。この名前は、Data Workbenchサーバーコンピューター上の名前付きプロファイルと一致する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors </td> 
   <td colname="col2"> <p><span class="wintitle">レポートサーバー</span>のエラーを電子メールで送信するSMTPサーバーのアドレスです。 </p> <p>例：<span class="filepath"> mail.mycompany.com </span> </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Password </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールの送信にログインが必要な場合を除き、このパラメーターはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Send From </td> 
   <td colname="col2"> <span class="wintitle">レポートサーバー</span>のエラーの送信元の電子メールアドレスです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Send To </td> 
   <td colname="col2"> <p>アラートの送信先の電子メールアドレス。 </p> <p>例：<span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Username </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザー名です。 メールの送信にログインが必要な場合を除き、このパラメーターはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ステータス間隔 </td> 
   <td colname="col2"> <p><span class="wintitle">レポートサーバー</span>が、ステータス情報を生成してdata workbenchサーバーに送信し、<span class="wintitle">詳細なステータス</span>に表示する頻度（秒）。 </p> <p>デフォルト値は 120 秒です。レポートキューの実行には数時間かかる場合があるので、2分などの小さな値に設定しないことをお勧めします。 この場合、600 ～ 1200秒の設定を考えてみてください。 </p> <p><span class="wintitle">詳細なステータス</span>について詳しくは、『Insightユーザーガイド</a>』の「管理インターフェイス」という章を参照してください。<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> </a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p><span class="keyword"> Report Server </span>が、プロファイルベクトルに示されたすべてのプロファイルを監視し、新しいレポートとアラートを受け取る頻度（分）。 デフォルト値は10分です。 </p> <p>指定した時間は、リストに表示されているすべてのプロファイルに分割されます。 例えば、間隔を10分に設定し、2つのプロファイルを監視する場合、各プロファイルは5分間監視されます。 新しいレポートや変更されたアラートがプロファイルに保存されたときにプロファイルが監視されている場合、そのレポートやアラートを即座に生成できます。 </p> <p><span class="wintitle"> [更新間隔</span>]が複数のプロファイルを監視するように設定されている場合、この設定は、設定された時間内にすべてのプロファイルを読み込むのに十分な高さに設定されていることが重要です。 大きなディメンションが多数設定されているシステムで、例えば、すべての要素名を持つ初期データ接続を取得するのに数分かかる場合は、この設定が、完全な同期が行われるまで十分な長さに設定されている必要があります。 そうしないと、プロファイルの同期エラーが発生します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
