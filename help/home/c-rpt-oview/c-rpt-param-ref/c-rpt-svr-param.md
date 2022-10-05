---
description: Report Server.cfg パラメーターについて説明します。
title: Report Server.cfg のパラメーター
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 8%

---

# Report Server.cfg のパラメーター{#report-server-cfg-parameters}

{{eol}}

Report Server.cfg パラメーターについて説明します。

サンプル [!DNL Report Server.cfg] 次に示す [Insight サーバーへの接続の設定](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) には、 [!DNL Report Server.cfg] ファイルに書き込まれます。

プロキシサーバーを通じてAdobeライセンスサーバーに接続する場合は、Licensing ベクトルとそのパラメーターを [!DNL Report Server.cfg]. 次に、Licensing ベクトルにモデルを使用できるこのベクトルとそのパラメータの例を示します。

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

次の表に、 [!DNL Report Server.cfg] ファイルパラメータ：

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel 拡張機能 </td> 
   <td colname="col2"> <p>次の Excel 拡張機能がサポートされています。 </p> <p>Excel 拡張子=文字列： <span class="filepath"> .xlsx </span> </p> <p>Excel 拡張子=文字列： <span class="filepath"> .xls </span> （デフォルト） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts </td> 
   <td colname="col2"> <p>（オプション）。フォントをリストするベクトル <span class="keyword"> レポートサーバー </span> は、UTF8 ベースの unicode 特殊文字をレンダリングするために使用する必要があります。 リスト内のフォント数に制限はありません。 </p> <p>先頭のフォントは常に Lucida Sans Console でなければなりません。このパラメーターが <span class="filepath"> Report Server.cfg </span> ファイル <span class="keyword"> レポートサーバー </span> は、Lucida Sans コンソールのみを使用してテキストを表示します。 </p> <p> <span class="keyword"> レポートサーバー </span> は、リストの最初のフォントを使用して、レンダリングできない文字が検出されるまで、すべての文字をレンダリングします。 次に、リスト内の 2 番目のフォントを使用して、その文字をレンダリングします。 そのフォントが文字をレンダリングしない場合、 <span class="keyword"> レポートサーバー </span> は、リスト内の 3 番目のフォントを使用して、その文字をレンダリングします。フォントリストの最後に到達するまで、このように繰り返します。 ベクトルに正しいフォントがリストされていない場合、 <span class="keyword"> レポートサーバー </span> 文字の 16 進値を表示します。 </p> <p> <p>注意：次の間は、このパラメーターに変更を加えない <span class="keyword"> レポートサーバー </span> が実行中です。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> ガンマ </span> 設定 <span class="filepath"> .png </span> ファイル出力。 デフォルト値は 1.6 です。 </p> <p> <p>注意：Adobeでは、この値を変更しないことをお勧めします。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing </td> 
   <td colname="col2"> <p>（オプション）。プロキシサーバーを通じてAdobeのライセンスサーバーに接続する場合にのみ、このベクトルのパラメータを変更する必要があります。 </p> <p>プロキシサーバーを介してAdobeのライセンスサーバーに接続するように設定したパラメータのセクション識別子。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> プロキシサーバーのアドレスです。 <span class="keyword"> レポートサーバー </span> は、を使用してAdobeのライセンスサーバーにアクセスする必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> （オプション）。次に関連付けられたパスワード： <span class="wintitle"> プロキシユーザー名 </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> プロキシサーバーのポート。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> （オプション）。プロキシサーバーへのアクセスに使用するユーザー名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Network Location </td> 
   <td colname="col2"> ネットワークの場所 <span class="keyword"> レポートサーバー </span> は、を使用してサーバーの共通名を IP アドレスに解決します。 ネットワークの場所は、Data Workbench サーバーコンピューター上の Addresses ディレクトリにあるアドレスファイルで定義されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サーバー </td> 
   <td colname="col2"> <p>どの Data Workbench サーバーコンピューターを設定するために設定するパラメーターのセクション識別子 <span class="keyword"> レポートサーバー </span> を接続してレポートを生成する必要があります。 このベクトルにリストされる項目の数を示す数値が含まれます。 </p> <p>各サーバーに serverInfo エントリを追加し、必要に応じてパラメーターを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> 対象となる Data Workbench サーバーコンピューターの IP アドレス <span class="keyword"> レポートサーバー </span> を接続してレポートを生成する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> 名前 <span class="keyword"> レポートサーバー </span> は内部的に data workbench サーバーを識別するためにを使用します。 これは単に内部ラベルなので、任意の名前を使用できます。 一貫性を保つために、サーバーの電子証明書に記載されている共通名を使用することをお勧めします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> ポート <span class="keyword"> レポートサーバー </span> は data workbench サーバーと通信します。 セキュア接続の場合、この値は通常 443 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシアドレス </td> 
   <td colname="col2"> プロキシサーバーのアドレスです。 <span class="keyword"> レポートサーバー </span> data workbench サーバーにアクセスするには、を使用する必要があります。 このパラメーターは、プロキシサーバーがサーバーマシンに接続する必要がある場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシパスワード </td> 
   <td colname="col2"> プロキシサーバーへのパスワード。このパラメーターは、Data Workbench サーバーのコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシポート </td> 
   <td colname="col2"> プロキシサーバーのポート。デフォルト値は 8080 です。このパラメーターは、Data Workbench サーバーのコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロキシユーザー名 </td> 
   <td colname="col2"> プロキシサーバーへのユーザー名です。 このパラメーターは、Data Workbench サーバーのコンピューターに接続するためにプロキシサーバーが必要な場合にのみ必要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> の SSL 証明書ファイルの名前 <span class="keyword"> レポートサーバー </span> マシン。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <span class="wintitle"> サーバーの共通名 </span> data workbench サーバーの電子証明書に記載されています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> Data Workbench サーバーと <span class="keyword"> レポートサーバー </span>. 選択肢は true または false です。デフォルト値は true です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果のメモリ制限 (KB) </td> 
   <td colname="col2"> <p>レポートおよびアラートで使用できるようにするメモリの量（KB 単位）。 デフォルト値は 50000 です。 </p> <p>レポートを実行する場合、 <span class="keyword"> レポートサーバー </span> は最初にこの値をチェックし、次に Maximum Slice Size パラメータの値をチェックします。 例えば、このパラメータを 50,000 に、最大スライスサイズを 50 に設定した場合、 <span class="keyword"> レポートサーバー </span> では、より多くのワークスペースを実行する領域を使用できる場合でも、一度に 50 個のワークスペースしか実行できません。 </p> <p> <p>注意：この制限は、Data Workbench サーバーの Query Memory Limit パラメーターで設定された値を超えないようにし、理想的には、 <span class="wintitle"> クエリメモリ制限 </span> 同時にレポートを実行する他のユーザーに何らかの余裕を提供する。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大スライスサイズ </td> 
   <td colname="col2"> 以下を実行できるレポートワークスペースの最大数 <span class="keyword"> レポートサーバー </span> は一度に実行できます。 デフォルト値は 50 です。詳しくは、 <span class="keyword"> レポートサーバー </span> この設定を使用する場合は、 <span class="wintitle"> 結果のメモリ制限 (KB) </span> パラメータの説明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software </td> 
   <td colname="col2"> <p>これを許可するかどうかを示します <span class="keyword"> レポートサーバの </span> data workbench サーバーが更新するソフトウェア。 選択肢は true または false です。デフォルト値は true です。 </p> <p>次に、モデルを使用できるこのパラメーターの例を示します。 </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> OpenGL ハードウェアレンダリングを使用 </td> 
   <td colname="col2"> <p>コントロール <span class="keyword"> レポートサーバー </span> は、ハードウェアレンダリング（マシンのグラフィックスカードなど）を使用して、レポート出力を生成します。 選択肢は true または false です。デフォルト値は true です。 </p> <p>このパラメータは、グラフィックスカードで問題が発生した場合にのみ、false に設定する必要があります。 false に設定した場合、 <span class="keyword"> レポートサーバー </span> はハードウェアレンダリングを使用しないので、デフォルトではソフトウェアレンダリングを使用します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポート </td> 
   <td colname="col2"> レポートを設定するために設定したパラメータのセクション識別子。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完了メッセージの間隔 </td> 
   <td colname="col2"> <p>使用する頻度（秒） <span class="keyword"> レポートサーバー </span> は、レポートまたはアラートの生成中にクエリが実行されたときに、完了ステータスメッセージを出力します。 デフォルト値は 120 秒です。 </p> <p>例：Workspace クエリは 62.145672%完了しました。 </p> <p>完了メッセージは <span class="filepath"> reportserver.log </span> とは、サーバーと同期されます。 この設定は、 <span class="filepath"> status.txt </span> 各レポートセットに対して前後に送信されるファイル。これにより、完了率をサムネールで表示できます。 メッセージは、レポートセットが完了したとき、または間隔に達したときに、いずれか早い方を先にして送信されます。 この値を大きく設定すると、サムネールによってクライアントインターフェイスで生成されたレポートの表示率は変わりませんが、表示される中間メッセージの数は変わります。 低い値を指定すると、データがから同期されるので、システムは大量のデータ同期に時間を費やす可能性があります。 <span class="keyword"> レポートサーバー </span> サーバーからプロファイルへ、すべての DPU および接続されたすべてのクライアントへ、 <span class="filepath"> status.txt </span> メッセージの変更。 </p> <p>システムは常に <span class="filepath"> status.txt </span> ファイルを作成します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プロファイル </td> 
   <td colname="col2"> <p>このベクトルにリストされる項目の数を示す数値。 レポートを作成するプロファイルごとに、 <span class="wintitle"> ReportProfile </span> Profiles ベクトルに入力し、 Server パラメーターと Profile パラメーターを設定します。 </p> <p> <span class="wintitle"> サーバー </span>  — 名前 <span class="keyword"> レポートサーバー </span> は内部的に data workbench サーバーを識別するためにを使用します。 この名前は、Data Workbench サーバーの SSL 証明書に一覧表示されるサーバーの共通名である必要があります。 </p> <p> <span class="wintitle"> プロファイル </span>  — レポートを作成するプロファイルの名前。 この名前は、Data Workbench サーバーコンピューター上の名前付きプロファイルと一致する必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーの SMTP サーバー </td> 
   <td colname="col2"> <p>送信元の SMTP サーバーのアドレス <span class="wintitle"> レポートサーバー </span> 電子メール経由のエラー。 </p> <p>例： <span class="filepath"> mail.mycompany.com </span> </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server for Errors Password </td> 
   <td colname="col2"> <p>SMTP サーバーにログインするためのパスワードです。 メールの送信にログインが必要でない場合、このパラメーターはオプションです。 </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信元のエラー用の SMTP サーバー </td> 
   <td colname="col2"> 送信元の電子メールアドレス <span class="wintitle"> レポートサーバー </span> エラー。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信先のエラー用の SMTP サーバー </td> 
   <td colname="col2"> <p>アラートの送信先の電子メールアドレス。 </p> <p>例： <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> エラーユーザー名用の SMTP サーバー </td> 
   <td colname="col2"> <p>SMTP サーバーにログインするためのユーザー名です。 メールの送信にログインが必要でない場合、このパラメーターはオプションです。 </p> <p>説明されている機能を使用するには、SMTP サーバーが必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ステータス間隔 </td> 
   <td colname="col2"> <p>使用する頻度（秒） <span class="wintitle"> レポートサーバー </span> に表示するステータス情報を生成し、data workbench サーバーに送信します。 <span class="wintitle"> 詳細なステータス </span>. </p> <p>デフォルト値は 120 秒です。レポートキューの実行に数時間かかる場合があるので、この値を小さな値（2 分など）に設定することはお勧めしません。 この場合、600 ～ 1200 秒の設定を考えてみましょう。 </p> <p>詳しくは、 <span class="wintitle"> 詳細なステータス </span>詳しくは、 <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight ユーザーガイド </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p>使用する頻度（分） <span class="keyword"> レポートサーバー </span> は、 Profiles ベクトルにリストされているすべてのプロファイルを監視し、新しいレポートおよびアラートを見つけます。 デフォルト値は 10 分です。 </p> <p>指定した時間は、リストに表示されているすべてのプロファイルで分割されます。 例えば、間隔を 10 分に設定し、2 つのプロファイルを監視する場合、各プロファイルは 5 分間監視されます。 新規または変更されたレポートやアラートがプロファイルに保存された際にプロファイルが監視されている場合、そのレポートやアラートをすぐに生成できます。 </p> <p>この <span class="wintitle"> 更新間隔 </span> は、複数のプロファイルを監視するように設定されています。この設定は、設定された時間内にすべてのプロファイルを読み込むのに十分な大きさにすることが重要です。 例えば、大きなディメンションが多数設定されているシステムで、すべての要素名を使用して初期データ接続を取得するのに数分かかる場合がある場合、この設定は完全に同期されるまでに十分な長さにする必要があります。 そうしないと、プロファイル同期エラーが発生します。 </p> </td> 
  </tr> 
 </tbody> 
</table>
