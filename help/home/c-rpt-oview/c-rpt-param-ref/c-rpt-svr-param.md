---
description: Report Server.cfgパラメーターに関する情報です。
solution: Analytics
title: Report Server.cfgのパラメーター
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Report Server.cfgのパラメーター{#report-server-cfg-parameters}

Report Server.cfgパラメーターに関する情報です。

「Insightサーバー [!DNL Report Server.cfg] への接続の [設定」に示すサンプルには](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) 、デフォルトでファイルに含まれるパラメー [!DNL Report Server.cfg] ターのみが含まれます。

プロキシサーバー経由でAdobe License Serverに接続する場合は、にLicensingベクトルとそのパラメーターを追加する必要がありま [!DNL Report Server.cfg]す。 次に、このベクトルとそのパラメーターの例を示します。このベクトルは、Licensingベクトルにモデルを使用できます。

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

次の表に、ファイルのパラメーターの説 [!DNL Report Server.cfg] 明を示します。

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
   <td colname="col2"> <p>次のExcel拡張機能がサポートされています。 </p> <p>Excel Extension = string: <span class="filepath"> .xlsx </span> </p> <p>Excel Extension = string: <span class="filepath"> .xls </span> （デフォルト） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts </td> 
   <td colname="col2"> <p>(オプション)Vector listing the fonts that <span class="keyword"> Report Server </span> should use to render UTF8-based unicode special characters. リスト内のフォント数に制限はありません。 </p> <p>先頭のフォントは常に Lucida Sans Console でなければなりません。If this parameter is not included in the <span class="filepath"> Report Server.cfg </span> file, <span class="keyword"> Report Server </span> uses only Lucida Sans console to display text. </p> <p> <span class="keyword"> Report Serverは、レ </span> ンダリングできない文字が検出されるまで、リストの最初のフォントを使用してすべての文字をレンダリングします。 次に、リスト内の2番目のフォントを使用してその文字をレンダリングします。 If that font does not render the character, <span class="keyword"> Report Server </span> uses the third font in the list to render that character, and so on, until it reaches the end of the font list. If the correct font is not listed in the vector, <span class="keyword"> Report Server </span> displays the hexidecimal value for the character. </p> <p> <p>注意： Report Serverの実行中は、このパラメーターを変 <span class="keyword"> 更しない </span> でください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> .pngフ </span> ァイル出 <span class="filepath"> 力のガ </span> ンマ設定。 デフォルト値は 1.6 です。 </p> <p> <p>注意： この値を変更することはお勧めしません。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing </td> 
   <td colname="col2"> <p>(オプション)このベクトルのパラメーターを変更する必要があるのは、プロキシサーバーを通じてアドビのライセンスサーバーに接続する場合のみです。 </p> <p>プロキシサーバーを介してアドビのライセンスサーバーに接続するように設定したパラメーターのセクション識別子。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> Report Serverがアドビのライセンスサーバーにア <span class="keyword"> クセスす </span> る際に使用する必要があるプロキシサーバーのアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> (オプション)The password associated with the <span class="wintitle"> Proxy User Name </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> プロキシサーバーのポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> (オプション)プロキシサーバーへのアクセスに使用するユーザー名です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Network Location </td> 
   <td colname="col2"> Report Serverがサーバーの共通 <span class="keyword"> 名をIP </span> アドレスに解決するために使用するネットワークの場所です。 ネットワークの場所は、Data Workbenchサーバーコンピューター上のAddressesディレクトリにあるアドレスファイルで定義されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバー </td> 
   <td colname="col2"> <p>レポートを生成するために接続する必要があるData WorkbenchサーバーコンピューターのReport Serverを設定するた <span class="keyword"> めに設定する </span> パラメーターのセクション識別子。 このベクトルには、このベクトルにリストされている項目の数を示す数値が含まれます。 </p> <p>各サーバーに対して、serverInfoエントリを追加し、必要に応じてパラメーターを設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> レポートを生成するためにレポートサーバーが接続する必要が <span class="keyword"> あるData Workbenchサ </span> ーバーコンピューターのIPアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> Data Workbenchサーバーを識 <span class="keyword"> 別するた </span> めにReport Serverが内部で使用する名前。 これは単なる内部ラベルなので、任意の名前を使用できます。 一貫性を保つため、サーバーのデジタル証明書に記載されている共通名を使用することをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Report ServerがData Workbenchサ <span class="keyword"> ーバーと </span> 通信する際に使用するポート。 安全な接続の場合、この値は通常443です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> The address of a proxy server that <span class="keyword"> Report Server </span> must use to access the data workbench server. このパラメーターは、サーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> プロキシサーバーへのパスワード。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> プロキシサーバーのポート。デフォルト値は 8080 です。このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> プロキシサーバーのユーザー名。 このパラメーターは、Data Workbenchサーバーコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> Report ServerコンピューターのSSL証明書フ <span class="keyword"> ァイルの </span> 名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <span class="wintitle"> Data Workbenchサーバーのデ </span> ジタル証明書に表示されるサーバー共通名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> Indicates whether SSL is used for secure communication between the data workbench server and <span class="keyword"> Report Server </span>. 選択肢は true または false です。デフォルト値は true です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果のメモリ制限(KB) </td> 
   <td colname="col2"> <p>レポートおよびアラートで使用可能にするメモリ量(KB)。 デフォルト値は 50000 です。 </p> <p>レポートの実行時に、 <span class="keyword"> Report Serverはま </span> ずこの値を確認し、次にMaximum Slice Sizeパラメーターの値を確認します。 例えば、このパラメーターを50,000に設定し、「最大スライスサイズ」を50に設定した場合、 <span class="keyword"></span> Report Serverでは、より多くのワークスペースを実行できる領域があっても、一度に実行できるワークスペースは50個までです。 </p> <p> <p>注意： この制限は、Data WorkbenchサーバーのQuery Memory Limitパラメーターで設定された値を超えないようにし、同時にレポートを実行する他のユーザーに少しの余裕を与えるために、 <span class="wintitle"></span> Query Memory Limitよりも少し小さく設定するのが理想的です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大スライスサイズ </td> 
   <td colname="col2"> Report Serverで一度に実行できるレポートワ <span class="keyword"> ークス </span> ペースの最大数です。 デフォルト値は 50 です。この設定をReport Serverで使用する方法 <span class="keyword"> につ </span> いて詳しくは、結果のメモリ制限(KB) <span class="wintitle"> パラメーターの説明を参照し </span> てください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software </td> 
   <td colname="col2"> <p>Indicates whether to allow this <span class="keyword"> Report Server's </span> software to be updated by the data workbench server. 選択肢は true または false です。デフォルト値は true です。 </p> <p>次に、モデルを使用できるこのパラメーターの例を示します。 </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGLハードウェアレンダリングの使用 </td> 
   <td colname="col2"> <p>Report Serverで、ハ <span class="keyword"> ードウェ </span> アレンダリング（マシンのグラフィックカードなど）を使用してレポート出力を生成するかどうかを制御します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>このパラメーターは、グラフィックカードに問題が発生した場合にのみfalseに設定する必要があります。 falseに設定した場合、Report Serverはハードウ <span class="keyword"> ェアレンダリ </span> ングを使用せず、デフォルトでソフトウェアレンダリングを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポート </td> 
   <td colname="col2"> レポートを設定するために設定するパラメーターのセクション識別子。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完了メッセージの間隔 </td> 
   <td colname="col2"> <p>レポートまたはアラートの生成中にクエ <span class="keyword"> リが実 </span> 行された場合に、Report Serverが完了ステータスメッセージを印刷する頻度（秒）。 デフォルト値は 120 秒です。 </p> <p>例：Workspaceクエリは62.145672%完了しています。 </p> <p>完了メッセージはreportserver.logに書き <span class="filepath"> 込まれ、サ </span> ーバーと同期されます。 この設定では、各レポー <span class="filepath"> トセット </span> の間で繰り返し送信されるstatus.txtファイルを制御し、完了率をサムネールと共に表示できるようにします。 レポートセットが完了したとき、または間隔に達したとき（いずれか早い方）に、メッセージが送信されます。 この値を大きく設定しても、サムネールによってクライアントインターフェイスで生成されたレポートの表示速度は変わりませんが、表示される中間メッセージの数は影響を受けます。 小さい値を指定すると、 <span class="keyword"> Report Serverからプロファイルにデータが同期され、 </span> status.txtメッセージが変更されるたびに、すべてのDPUおよび接続されているすべてのクライアントにデータが同期されるので、システムでデータの同期に大量の時間がかか <span class="filepath"></span> ります。 </p> <p>この設定パラメータの設定に関係なく、レポートセットが完 <span class="filepath"></span> 了すると、システムは常にstatus.txtファイルを送信します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>このベクトルにリストされている項目の数を示す数値です。 レポートを作成する各プロファイルに対して、Profilesベクトルに <span class="wintitle"> ReportProfileエ </span> ントリを追加し、ServerパラメーターとProfileパラメーターを設定します。 </p> <p> <span class="wintitle"> サーバ </span> ー — Data Workbenchサー <span class="keyword"> バーを識別す </span> るためにReport Serverが内部的に使用する名前。 この名前は、Data WorkbenchサーバーのSSL証明書に記載されているサーバー共通名である必要があります。 </p> <p> <span class="wintitle"> プロフ </span> ァイル — レポートを作成する対象のプロファイルの名前。 この名前は、Data Workbenchサーバーコンピューター上の名前付きプロファイルと一致する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors </td> 
   <td colname="col2"> <p>電子メールでReport Serverエラーを送信するSMTPサーバー <span class="wintitle"> のアド </span> レスです。 </p> <p>例： <span class="filepath"> mail.mycompany.com </span> </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Password </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのパスワードです。 メールの送信にログインが必要でない限り、このパラメータはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Send From </td> 
   <td colname="col2"> Report Serverエラーの送信元の電子メール <span class="wintitle"> アドレス </span> です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server For Errors Send To </td> 
   <td colname="col2"> <p>アラートの送信先の電子メールアドレス。 </p> <p>例： <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Username </td> 
   <td colname="col2"> <p>SMTPサーバーにログインするためのユーザー名です。 メールの送信にログインが必要でない限り、このパラメータはオプションです。 </p> <p>SMTPサーバーは、説明された機能を使用するために必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ステータス間隔 </td> 
   <td colname="col2"> <p>Report Serverがステータス情報を生成し、 <span class="wintitle"> Data Workbenchサ </span> ーバーに送信して詳細なステータスで表示する頻度（秒） <span class="wintitle"> です </span>。 </p> <p>デフォルト値は 120 秒です。レポートキューの実行には時間がかかる場合があるので、2分などの小さな値に設定することはお勧めしません。 この場合、600 ～ 1200秒の設定を考えてみましょう。 </p> <p>詳細なステータスについて詳 <span class="wintitle"> しくは、『Insight </span>ユーザーガイド』の「管理インターフェイス」という章を <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> 参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p>Report Serverが、Profilesベクトルにリストされているす <span class="keyword"> べてのプ </span> ロファイルで、新しいレポートおよびアラートを監視する頻度（分単位）です。 デフォルト値は10分です。 </p> <p>指定した時間は、一覧に表示されるすべてのプロファイルに分割されます。 例えば、間隔を10分に設定し、2つのプロファイルを監視する場合、各プロファイルは5分間監視されます。 新しいまたは変更されたレポートやアラートがプロファイルに保存されたときにプロファイルが監視されている場合、そのレポートやアラートは即座に生成できます。 </p> <p>「更新間隔」 <span class="wintitle"> が複数のプ </span> ロファイルを監視するように設定されている場合は、この設定が、設定された時間内にすべてのプロファイルを読み込むのに十分な高さに設定されていることが重要です。 例えば、大きなディメンションが多数設定されたシステムでは、すべての要素名を持つ初期データ接続を取得するのに数分かかる場合があり、この設定は完全な同期が行われるまで十分な長さにする必要があります。 そうしないと、プロファイルの同期エラーが発生します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

