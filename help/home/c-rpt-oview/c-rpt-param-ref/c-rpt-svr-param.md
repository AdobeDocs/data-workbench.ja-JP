---
description: Report Server.cfgパラメーターについて取り上げます。
title: Report Server.cfg のパラメーター
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 8%

---

# Report Server.cfg のパラメーター{#report-server-cfg-parameters}

Report Server.cfgパラメーターについて取り上げます。

[Insightサーバーへの接続の設定](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)に示すサンプル[!DNL Report Server.cfg]には、デフォルトで[!DNL Report Server.cfg]ファイルに含まれているパラメーターのみが含まれています。

プロキシサーバを通じてAdobeライセンスサーバに連絡する場合は、[!DNL Report Server.cfg]にライセンスベクトルとそのパラメータを追加する必要があります。 次に、Licensingベクトルにモデルを使用できるこのベクトルとそのパラメータの例を示します。

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
   <td colname="col2"> <p>次のExcel拡張機能がサポートされています。 </p> <p>Excel拡張子=文字列：<span class="filepath"> .xlsx </span> </p> <p>Excel拡張子=文字列：<span class="filepath"> .xls </span> （デフォルト） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts </td> 
   <td colname="col2"> <p>（オプション。<span class="keyword"> Report Server </span>がUTF8ベースのUnicode特殊文字をレンダリングする際に使用するフォントをリストするベクトル。 リスト内のフォント数に制限はありません。 </p> <p>先頭のフォントは常に Lucida Sans Console でなければなりません。このパラメーターが<span class="filepath"> Report Server.cfg </span>ファイルに含まれていない場合、 <span class="keyword">レポートサーバー</span>はLucida Sansコンソールのみを使用してテキストを表示します。 </p> <p> <span class="keyword"> Report Serverは、リ </span> スト内の最初のフォントを使用して、レンダリングできない文字が検出されるまで、すべての文字をレンダリングします。次に、リスト内の2番目のフォントを使用して、その文字をレンダリングします。 そのフォントが文字をレンダリングしない場合、 <span class="keyword"> Report Server </span>は、リスト内の3番目のフォントを使用してその文字をレンダリングします。その後、フォントリストの最後に達するまで同様にレンダリングします。 正しいフォントがベクトルにリストされていない場合、 <span class="keyword">レポートサーバー</span>はその文字の16進値を表示します。 </p> <p> <p>注意： <span class="keyword">レポートサーバー</span>の実行中は、このパラメーターを変更しないでください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> .pngフ </span> ァイル出力 <span class="filepath"> のガンマ </span> 設定。デフォルト値は 1.6 です。 </p> <p> <p>注意： Adobeは、この値を変更しないことをお勧めします。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing </td> 
   <td colname="col2"> <p>（オプション。プロキシサーバーを介してAdobeのライセンスサーバーに接続する場合にのみ、このベクトルのパラメータを変更する必要があります。 </p> <p>プロキシサーバーを介してAdobeのライセンスサーバーに接続するように設定したパラメータのセクション識別子。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がAdobeのライセンスサーバーにアクセスする際に使用する必要があるプロキシサーバーのアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> （オプション。<span class="wintitle">プロキシユーザー名</span>に関連付けられているパスワード。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> プロキシサーバーのポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> （オプション。プロキシサーバーへのアクセスに使用するユーザー名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Network Location </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がサーバーの共通名をIPアドレスに解決するために使用するネットワークの場所。 ネットワークの場所は、Data Workbenchサーバーコンピューター上のAddressesディレクトリにあるアドレスファイルで定義されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバー </td> 
   <td colname="col2"> <p>レポートを生成するために接続する必要があるData Workbenchサーバーマシン<span class="keyword">レポートサーバー</span>を設定するために設定するパラメーターのセクション識別子。 これには、このベクトルにリストされる項目の数を示す数値が含まれます。 </p> <p>各サーバーにserverInfoエントリを追加し、必要に応じてパラメーターを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> レポートを生成するために<span class="keyword">レポートサーバー</span>が接続する必要があるData WorkbenchサーバーコンピューターのIPアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>が内部的にData Workbenchサーバーを識別するために使用する名前。 これは単に内部ラベルなので、任意の名前を使用できます。 一貫性を保つために、サーバーの電子証明書に記載されている共通名を使用することをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がData Workbenchサーバーと通信するポート。 安全な接続の場合、この値は通常443です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシアドレス </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>がData Workbenchサーバーにアクセスする際に使用する必要があるプロキシサーバーのアドレス。 このパラメーターは、プロキシサーバーがサーバーマシンに接続する必要がある場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシパスワード </td> 
   <td colname="col2"> プロキシサーバーへのパスワード。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシポート </td> 
   <td colname="col2"> プロキシサーバーのポート。デフォルト値は 8080 です。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシユーザー名 </td> 
   <td colname="col2"> プロキシサーバーへのユーザー名。 このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>コンピューターのSSL証明書ファイルの名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <span class="wintitle"> Data Workbenchサーバー </span> のデジタル証明書に一覧表示されるサーバー共通名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> Data Workbenchサーバーと<span class="keyword">レポートサーバー</span>間の安全な通信にSSLが使用されるかどうかを示します。 選択肢は true または false です。デフォルト値は true です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果のメモリ制限(KB) </td> 
   <td colname="col2"> <p>レポートおよびアラートで使用可能にするメモリ量(KB)。 デフォルト値は 50000 です。 </p> <p>レポートを実行する際、<span class="keyword"> Report Server </span>はまずこの値を確認し、次にMaximum Slice Sizeパラメータの値を確認します。 例えば、このパラメーターを50,000に設定し、スライスの最大サイズを50に設定した場合、追加のワークスペースを実行できる領域があっても、<span class="keyword">レポートサーバー</span>では一度に50個のワークスペースしか実行されません。 </p> <p> <p>注意： この制限は、Data WorkbenchサーバーのQuery Memory Limitパラメーターに設定された値を超えないでください。また、同時にレポートを実行する他のユーザーには、 <span class="wintitle"> Query Memory Limit </span>より少し小さく設定することが理想的です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大スライスサイズ </td> 
   <td colname="col2"> <span class="keyword">レポートサーバー</span>が一度に実行できるレポートワークスペースの最大数。 デフォルト値は 50 です。<span class="keyword">レポートサーバー</span>でこの設定がどのように使用されるかについて詳しくは、 <span class="wintitle">結果のメモリ制限(KB) </span>パラメーターの説明を参照してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software </td> 
   <td colname="col2"> <p>この<span class="keyword">レポートサーバーの</span>ソフトウェアをData Workbenchサーバーによって更新するかどうかを示します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>次に、モデルを使用できるこのパラメーターの例を示します。 </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGLハードウェアレンダリングを使用 </td> 
   <td colname="col2"> <p><span class="keyword">レポートサーバー</span>がハードウェアレンダリング（マシンのグラフィックカードなど）を使用してレポート出力を生成するかどうかを制御します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>このパラメーターは、グラフィックカードに問題がある場合にのみfalseに設定する必要があります。 falseに設定した場合、 <span class="keyword">レポートサーバー</span>はハードウェアレンダリングを使用しないで、デフォルトでソフトウェアレンダリングを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポート </td> 
   <td colname="col2"> レポートを設定するために設定したパラメーターのセクション識別子。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完了メッセージの間隔 </td> 
   <td colname="col2"> <p>レポートまたはアラートの生成中にクエリが実行される際に、<span class="keyword">レポートサーバー</span>が完了ステータスメッセージを出力する頻度（秒）。 デフォルト値は 120 秒です。 </p> <p>例：ワークスペースクエリは62.145672%完了しました。 </p> <p>完了メッセージは<span class="filepath"> reportserver.log </span>に書き込まれ、サーバーに同期されます。 この設定は、各レポートセットに対して前後に送信される<span class="filepath"> status.txt </span>ファイルを制御し、完了率がサムネールで表示されるようにします。 メッセージは、レポートセットが完了したとき、または間隔に達したときに、いずれか早い方のタイミングで送信されます。 この値を大きく設定すると、クライアントインターフェイスでサムネールによって生成されたレポートの表示レートは変わりませんが、表示される中間メッセージの数は変わります。 値を小さく指定すると、<span class="keyword"> Report Server </span>サーバーからプロファイルにデータが同期され、<span class="filepath"> status.txt </span>メッセージが変更されるたびに、すべてのDPUと接続されているすべてのクライアントにデータが同期されるので、システムではデータの同期に長い時間がかかります。 </p> <p>この設定パラメーターの設定に関係なく、レポートセットが完了すると、システムは常に<span class="filepath"> status.txt </span>ファイルを送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>このベクトルにリストされる項目の数を示す数値。 レポートを作成するプロファイルごとに、 Profilesベクトルに<span class="wintitle"> ReportProfile </span>エントリを追加し、 ServerパラメーターとProfileパラメーターを設定します。 </p> <p> <span class="wintitle"> サーバ </span> ー — Report Serverが内部的に <span class="keyword"> Data Workbenchサ </span> ーバーを識別するために使用する名前。この名前は、Data WorkbenchサーバーのSSL証明書に一覧表示されるサーバーの共通名である必要があります。 </p> <p> <span class="wintitle"> プロフ </span> ァイル — レポートを作成する対象のプロファイルの名前。この名前は、Data Workbenchサーバーコンピューター上の名前付きプロファイルと一致する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーのSMTPサーバー </td> 
   <td colname="col2"> <p>電子メールで<span class="wintitle">レポートサーバー</span>エラーを送信するSMTPサーバーのアドレス。 </p> <p>例：<span class="filepath"> mail.mycompany.com </span> </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Password </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールを送信するためにログインが必要でない限り、このパラメーターはオプションです。 </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元のエラーのSMTPサーバー </td> 
   <td colname="col2"> <span class="wintitle">レポートサーバー</span>エラーの送信元の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTPサーバーへの送信エラー </td> 
   <td colname="col2"> <p>アラートの送信先の電子メールアドレス。 </p> <p>例：<span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Username </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザー名です。 メールを送信するためにログインが必要でない限り、このパラメーターはオプションです。 </p> <p>説明した機能を使用するには、SMTPサーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ステータス間隔 </td> 
   <td colname="col2"> <p><span class="wintitle">レポートサーバー</span>がステータス情報を生成してData Workbenchサーバーに送信し、<span class="wintitle">詳細なステータス</span>に表示する頻度（秒）です。 </p> <p>デフォルト値は 120 秒です。レポートキューの実行には数時間かかる場合があるので、この値を小さな値（2分など）に設定することはお勧めしません。 この場合、600 ～ 1200秒の設定を考えてみましょう。 </p> <p><span class="wintitle">詳細なステータス</span>について詳しくは、『<a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insightユーザーガイド</a>』の「管理インターフェイス」の章を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p><span class="keyword"> Report Server </span>がProfilesベクトルにリストされているすべてのプロファイルで新しいレポートおよびアラートを監視する頻度（分単位）です。 デフォルト値は10分です。 </p> <p>指定した時間は、リストに表示されているすべてのプロファイルで分割されます。 例えば、間隔を10分に設定し、2つのプロファイルを監視する場合、各プロファイルは5分間監視されます。 新しいレポートや変更されたレポートやアラートがプロファイルに保存されたときにプロファイルが監視されている場合は、レポートやアラートをすぐに生成できます。 </p> <p><span class="wintitle">更新間隔</span>が複数のプロファイルを監視するように設定されている場合、この設定は、設定された時間内にすべてのプロファイルを読み込むのに十分な大きさにすることが重要です。 多くの大きなディメンションが設定されているシステムで、例えば、すべての要素名を使用して最初のデータ接続を取得するのに数分かかる場合は、この設定が完全に同期されるまでに十分な時間が必要です。 そうしないと、プロファイルの同期エラーが発生します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
