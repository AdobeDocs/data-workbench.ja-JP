---
description: Report.cfg パラメーターについて説明します。
title: Report.cfg のパラメーター
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 4%

---

# Report.cfg のパラメーター{#report-cfg-parameters}

{{eol}}

Report.cfg パラメーターについて説明します。

サンプル [!DNL Report.cfg] 次に示す [レポートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) には、 [!DNL Report.cfg] ファイルに書き込まれます。 次の表に、使用可能なすべての [!DNL Report.cfg] ファイルのパラメーター。

追加のパラメーターを [!DNL Report.cfg] ファイルに書き込む場合は、テキストエディターを使用する必要があります。 その手順（各パラメーターエントリの定義方法の例を含む）については、 [既存の Report.cfg ファイルの編集](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>この表のパラメータは、アルファベット順に一覧表示されます。 を開くと、 [!DNL Report.cfg] ファイルのData Workbenchを指定すると、ベクトルはアルファベット順に並べられ、その後に個々のパラメータがアルファベット順に並べられます。

<table id="table_F55E925EA34F43B6832788BB6878BB4A">
 <thead>
  <tr>
   <th colname="col1" class="entry"> パラメーター </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> アラートしきい値 </td>
   <td colname="col2"> <p><i>オプション</i>。このパラメーターは、指標指標を含むレポートにのみ適用されます。 アラートレポートを送信する前にワークシートに表示する必要がある指標の数。 </p> <p>指標インジケーターのワークシートで 1 つの指標のみが監視されている場合は、しきい値を 1 に設定します。 レポートは、シート内の指標が上下矢印または X と評価されると生成されます。レポート内で複数の指標が監視されている場合は、レポートが生成される前に上下矢印または X に評価する必要がある指標の数を選択できます。 例えば、2 つの指標が監視されている場合は、次のようになります。
     <ul id="ul_A64E8A2306B14371A233D372B956F64D">
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">しきい値を 1 に設定すると、シート内の指標のいずれかが上下の矢印または X に評価された場合に、レポートが生成されます。 </li>
      <li id="li_DA4EF4984880483DA48322D9D57B9240">しきい値を 2 に設定した場合、レポートが生成される前に、両方の指標が上向き/下向き矢印または X に評価される必要があります。 </li>
     </ul> </p> <p>指標指標について詳しくは、 <i>Data Workbenchユーザーガイド</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> レポートの再生成を許可 </td>
   <td colname="col2"> <p>を示します <span class="keyword"> レポートサーバー </span> これらのレポートを作成または変更すると、特定のレポートが自動的に生成または再生成されます。 選択肢は true または false です。true に設定した場合、レポートワークスペースの作成または変更が原因で発生します <span class="keyword"> レポートサーバー </span> を使用して最新の実行のレポートを再生成します。 </p> <p> <p>注意：変更 <span class="filepath"> Report.cfg </span> ファイルの原因 <span class="keyword"> レポートサーバー </span> それによって管理されるすべてのレポートを再生成する <span class="filepath"> Report.cfg </span> ファイル。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 添付ファイル </td>
   <td colname="col2"> <p><i>オプション</i>。添付ファイルの数を含む、E メールで配信されたレポートで送信される添付ファイルの名前とコンテンツタイプのセクション識別子。 </p> <p>新しい添付ファイルを追加するには：
     <ol id="ol_CBDC1E95D34A4D08A862680127438433">
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">を開きます。 <span class="filepath"> Report.cfg </span> ファイルをData Workbench </li>
      <li id="li_0709ADDDDF2E469FAB10761B46173136">右クリック <span class="uicontrol"> 添付ファイル </span> をクリックし、 <span class="uicontrol"> 新しい子を追加 </span> &gt; <span class="uicontrol"> 添付ファイル </span>. </li>
     </ol> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> コンテンツタイプ </td>
   <td colname="col2"> <p>添付するファイルのコンテンツタイプ。 </p> <p>例：image/jpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> FileName </td>
   <td colname="col2"> <p>添付するファイルの場所と名前。 </p> <p>例： <span class="filepath"> c:\myimage.jpg </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Color Set </td>
   <td colname="col2"> 使用する配色を指定します <span class="filepath"> .png </span> ファイル。 0 は黒の背景用、1 は白の背景用、2 はグレースケール画像用です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 実行するコマンド </td>
   <td colname="col2"> <i>オプション</i>。レポートセットの生成後に実行されるバッチコマンドまたは実行可能ファイル。 コマンドシェルインタープリタの起動が必要な場合は、コマンドの前に cmd /c を付けます。 </td>
  </tr>
  <tr>
   <td colname="col1"> デフォルトの Excel テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>。汎用 Excel テンプレートファイルのファイル名 ( <span class="filepath"> .xls </span> または <span class="filepath"> .xlsx </span>) をクリックします。 このパラメーターは、次のような完全なファイルパスをサポートします。 <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>このファイルは、特定のレポート用にテンプレートが定義されていない限り、すべての Excel レポートで使用されます。 詳しくは、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> テンプレートファイルの使用 </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ディメンション名 </td>
   <td colname="col2"> <i>オプション</i>。レポートを動的に生成するディメンションの名前。 このパラメーターにディメンション名を入力する場合は、「参照ファイル」パラメーターまたは「上位 N 件の指標」および「上位 N 件の値」パラメーターのいずれかに値を入力する必要があります。 このパラメーターで名前を付けたディメンションは、レポートを作成するデータセット内に存在する必要があります。 </td>
  </tr>
  <tr>
   <td colname="col1"> 完璧な場合のみメール送信 </td>
   <td colname="col2"> <i>オプション</i>。実行中にエラーが発生しなかった場合にのみレポートセットを送信するようにユーザーが指定できます。 選択肢は true と false です。デフォルト値は false です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 終了日 </td>
   <td colname="col2"> <p><i>オプション</i>。レポートセットを実行する最後の日時です。 今回は、データセットの基準日時に基づいています。 </p> <p>形式：MM/DD/YYYY hh:mm タイムゾーン（時間の 24 時間構文を使用） </p> <p>例：08/01/2007 12:01 EDT </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 毎 </td>
   <td colname="col2"> レポートセット生成の頻度：日、週、月。 </td>
  </tr>
  <tr>
   <td colname="col1"> Excel ウォッチドッグのタイムアウト（秒） </td>
   <td colname="col2"> <p><i>オプション</i>。目的の秒数 <span class="keyword"> レポートサーバー </span> ：以前に Excel ファイルとしてレポートを生成する際に、Microsoft Excel が応答するのを待つ <span class="keyword"> レポートサーバー </span> は Excel が応答しないことを決定し、プロセスを終了します。 このパラメーターを使用すると、が有効になります <span class="keyword"> レポートサーバー </span> ：応答しなくなった Excel を終了し、Excel 以外のレポートの処理を続行する場合。 デフォルトは 300.0 です。この機能を無効にするには、このパラメーターを 0.0 に設定します。 </p> <p>定義した値が、レポートを Excel にエクスポートできるだけの長さであることを確認します。 それ以外の場合は、 <span class="keyword"> レポートサーバー </span> が Excel を途中で終了する可能性があり、レポートは生成されません。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> フィルター式 </td>
   <td colname="col2"> <p><i>オプション</i>。レポートセット内のすべてのワークスペースに適用されるフィルター。 </p> <p>詳しくは、 <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> フィルター作成の構文 </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ガンマ補正 </td>
   <td colname="col2"> <p>のガンマ設定 <span class="filepath"> .png </span> ファイル出力。 デフォルトは 1.6 です。 </p> <p> <p>注意：Adobeでは、この値を変更しないことをお勧めします。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ロゴを隠す </td>
   <td colname="col2"> レポート生成時に、レポートサーバーでロゴを非表示にするかどうかを示します。 オプションは次のとおりです。 <span class="filepath"> true </span> または <span class="filepath"> false </span>. 次に設定した場合： <span class="filepath"> false </span>をクリックした場合、レポートはレポートのロゴで生成されます。 初期設定は <span class="filepath">false</span> です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 参照ファイル </td>
   <td colname="col2"> <p><i>オプション</i>。このパラメーターを入力すると、レポートサーバーは動的モードで実行され、「Dimension名」パラメーターで指定されたディメンションの各要素に関するレポートが生成されます。 このファイルには、ヘッダー行のない、タブ区切りの 2 つの列が含まれている必要があります。 </p> <p>
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A">
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">列 1 には、ディメンション要素のリストが含まれます。 </li>
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">列 2 には、レポートの受信者の電子メールアドレスが含まれます。 列 1 の特定の要素に関するレポートが、列 2 の同じ行にある電子メールアドレスに送信されます。 複数の電子メールアドレスを入力する場合は、コンマで区切ります（スペースは使用できません）。 レポートを電子メールで送信しない場合、この列は空にすることができますが、存在する必要があります。 </li>
     </ul> </p> <p> <p>注意：このパラメータに値を入力する場合は、[Dimension名 ] パラメータに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 通知のみ </td>
   <td colname="col2"> この <span class="wintitle"> レポートサーバー </span> を設定すると、レポートの生成時に電子メールを送信するよう data workbench を設定できます。 この値を <span class="filepath"> true </span> はレポートを送信せず、購読ユーザーに対してレポートが生成されたことを通知する電子メールを送信します。 </td>
  </tr>
  <tr>
   <td colname="col1"> メールレポート </td>
   <td colname="col2"> <p>電子メールでレポートを配信するためのセクション識別子。 レポートを電子メールで配布するには、 <span class="wintitle"> メールレポート </span> エントリ。 レポートセット内のすべてのレポートは、「受信者」パラメーターで指定された電子メールアドレス宛てに、1 つのメッセージで電子メールで送信されます。 </p> <p> <p>注意：レポートサーバーは、1 つ以上のレポートが生成された場合にのみ電子メールを送信します。 </p> </p> <p>レポートの電子メール送信を有効にするには、このエントリに対して、少なくとも次のパラメーターを設定する必要があります。
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8">
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP サーバー </li>
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">受信者 </li>
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">送信者のアドレス </li>
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">通知のみ </li>
     </ul> </p> <p> <p>注意：レポートセットを再生成した後に電子メールでレポートを送信するには、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> 既存の Report.cfg ファイルの編集 </a>. </p> </p> <p>「通知のみ」の値は、5.4x および 5.5x リリースで使用できます。 </p> <p>多数の受信者に通知を送信する場合（20 人以上）は、E メール配信リストを使用することを強くお勧めします。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 本文 XSL テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>。次に適用する XSL テンプレートファイルのパス <span class="filepath"> reports.xml </span> ファイル。 このパラメーターを使用すると、Report Server は、添付ファイルではなく、配信済みの電子メール内でレポートを送信できます。 結果のテキストは、E メールメッセージの本文として使用されます。 </p> <p>詳しくは、 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> レポートサンプルファイル </a> を参照してください。 </p> <p>XSLT(Extensible Stylesheet Language) について詳しくは、 <a href="https://www.w3.org/Style/XSL/" format="http" scope="external"> 拡張スタイルシート言語ファミリ </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 受信者 </td>
   <td colname="col2"> レポートの送信先となる人の電子メールアドレス。 </td>
  </tr>
  <tr>
   <td colname="col1"> 送信者のアドレス </td>
   <td colname="col2"> 送信者の E メールアドレス。 </td>
  </tr>
  <tr>
   <td colname="col1"> 送信者名 </td>
   <td colname="col2"> （オプション）。送信者の名前。 </td>
  </tr>
  <tr>
   <td colname="col1"> SMTP サーバー </td>
   <td colname="col2"> SMTP サーバーマシンのアドレスと、認証に必要なパスワードとユーザー名。 </td>
  </tr>
  <tr>
   <td colname="col1"> 件名 </td>
   <td colname="col2"> <i>オプション</i>。送信する E メールを説明する件名。 </td>
  </tr>
  <tr>
   <td colname="col1"> 通知のみ </td>
   <td colname="col2"> バックグラウンドレポートの生成時に電子メールを送信するように Data Workbench を設定できます。 この値を True に設定すると、レポートが送信されず、購読ユーザーをレポートの場所にリンクする電子メールが送信されます。 </td>
  </tr>
  <tr>
   <td colname="col1"> 出力ルート </td>
   <td colname="col2"> <p><i>オプション</i>。生成されたレポートセットの出力場所。 デフォルトは <i>&lt;profile name=""&gt;</i>\Report Server のインストールディレクトリ内の Reports フォルダ。 </p> <p>を設定するには、以下を実行します。 <span class="keyword"> レポートサーバー </span> レポートをポータルに出力するには、 <span class="wintitle"> 出力ルート </span> をポータルに使用する web サーバーのドキュメントルートに追加します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> クエリフィルターをプリロード </td>
   <td colname="col2"> <p><i>オプション</i>。このパラメーターは、 <span class="wintitle"> トップDimension要素 </span> レポートタイプ。 </p> <p>レポートを生成する前に、上位 N 個のディメンション要素を決定するために実行する必要があるクエリに適用するフィルターの名前。 デフォルトはです。 <span class="wintitle"> Broken_Session_Filter </span>. 詳しくは、 <span class="wintitle"> ブロークンセッションフィルター </span>を参照し、 <i>Data Workbenchユーザーガイド</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <span class="wintitle"> レポートタイプ </span> </td>
   <td colname="col2"> <p>出力を生成する形式を指定します。 次のオプションを使用するか、すべて使用して、レポートセットを複数の形式で一度に出力できます。
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9">
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel では、ワークシートごとに 1 つのビジュアライゼーションを持つ Excel ブックが作成されます。 原則として、Excel ファイルを電子メール配信に使用します。 詳しくは、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Microsoft Excel ファイルとしてのレポートの生成 </a>. テンプレートファイルの使用について詳しくは、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> テンプレートファイルの使用 </a>. </li>
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png は Portable Network Graphic ファイルを作成します。 原則として、 <span class="filepath"> .png </span> web ブラウザー（ポータル）に表示するファイル。 </li>
      <li id="li_869DA266E6A041A5BD343537743FAC79">サムネールがサムネールを作成します ( <span class="filepath"> .jpg </span> ファイル ) を含める必要があります。 デフォルトのサイズは 240x180 です。 デフォルトのサイズを変更するには、「サムネール X」および「サムネール Y」パラメーターを編集します。 </li>
     </ul> </p> <p>編集時に新しいレポートタイプを追加するには <span class="filepath"> Report.cfg </span> data workbench で、右クリック <span class="uicontrol"> レポートタイプ </span>をクリックし、 <span class="uicontrol"> 新しい子を追加 </span>をクリックし、目的のレポートタイプを選択します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 開始日 </td>
   <td colname="col2"> <p>レポートセットを実行する最初の日時です。 今回は、データセットの基準日時に基づいています。 </p> <p>形式：MM/DD/YYY hh:mm タイムゾーン（時間の 24 時間構文を使用） </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> <p> <p>注意：プロファイル内のデータのタイムスタンプが指定した日時と一致すると、レポートの実行が開始されます。 </p> </p> <p>例： </p> <p>開始日が08/08/2006 12:00 EST の場合、タイムスタンプが08/08/2006 12:00 EST 以降のデータに対してレポートが実行されます。
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1">
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">日別レポートは08/08/2006で実行され、その後は hh:mm = 12:00 EST のデータで毎日実行されます。 </li>
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">週別レポートは08/08/2006で、その後 7 日ごとに hh:mm = 12:00 EST のデータで実行されます。 </li>
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月別レポートは08/08/2006で、その後は毎月 8 日目に hh:mm = 12:00 EST のデータで実行されます。 </li>
     </ul> </p> <p>この <span class="wintitle"> レポート時間 </span> 指標は、「過去 7 日間」、「昨日」、「3 週間前」などの、「最近 N」のレポートディメンションに影響します。 レポートサーバーのクエリの場合、 <span class="wintitle"> レポート時間 </span> 指標 ( <span class="filepath"> レポート時間.metric </span>) は、レポートが実行される日時を示します。 これは、最初は Start Date パラメーターで指定された日時で、次に Every パラメーターで指定された期間だけ増分されます。 Data Workbench のクエリの場合、 <span class="wintitle"> レポート時間 </span> 指標は、基準日指標の午前 0 時 ( <span class="filepath"> 基準日.metric </span>) をクリックします。 レポート時間指標の定義の違いにより、Last N ディメンションを使用するワークスペースに対してクエリを実行すると、Data Workbench で異なる結果を受け取ることができます。 <span class="keyword"> レポートサーバー </span> 同じワークスペースの </p> </td>
  </tr>
  <tr>
   <td colname="col1"> サムネール X </td>
   <td colname="col2"> <i>オプション</i>。出力として生成されるサムネールの X 軸のサイズ（ピクセル単位）を制御する整数。 </td>
  </tr>
  <tr>
   <td colname="col1"> サムネール Y </td>
   <td colname="col2"> <i>オプション</i>。出力として生成されるサムネールの Y 軸のサイズ（ピクセル単位）を制御する整数。 </td>
  </tr>
  <tr>
   <td colname="col1"> 上位 N 件の指標 </td>
   <td colname="col2"> <p><i>オプション</i>。Top N 値パラメータの説明を参照してください。 </p> <p> <p>注意：このパラメータに値を入力する場合は、[Dimension名 ] パラメータと [ 上位 N 値 ] パラメータに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 上位 N 値 </td>
   <td colname="col2"> <p><i>オプション</i>。このパラメーターを入力すると、 <span class="keyword"> レポートサーバー </span> は動的モードで実行され、Dimension名パラメーターで指定されたディメンションの要素の上位の数（このパラメーターで指定）に関するレポートを生成します（Top N Metric パラメーターで指定された指標でカウント）。 </p> <p>例：Dimension名パラメーターに「Page」、「Top N Metric」パラメーターに「Sessions」、およびこのパラメーターに「5」と入力した場合、生成されるレポートには、セッション数が最も多い上位 5 つのページが表示されます。 </p> <p> <p>注意：このパラメーターに値を入力する場合は、「Dimension名」パラメーターと「上位 N 件の指標」パラメーターに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ローカルサンプルのみを使用 </td>
   <td colname="col2"> <i>オプション</i>。必要かどうかを示します <span class="keyword"> レポートサーバー </span> データセットのローカルサンプルのみを使用してレポートを生成する場合。 このパラメーターを true に設定すると、（data workbench サーバーに負荷をかけずに）レポートセットのサンプルを表示して、データを完全に処理するのに必要な時間をかけずに、出力の見え方を確認できます。 これはテスト関数として機能します。 選択肢は true または false です。デフォルトは false です。 </td>
  </tr>
  <tr>
   <td colname="col1"> ワークスペースパス </td>
   <td colname="col2"> <p><i>オプション</i>。特定のレポートセットのワークスペースのコレクションの場所。 これは、 <span class="filepath"> Report.cfg </span> 複数のレポートセット用のファイル このパスのルートディレクトリには、任意のプロファイルフォルダーを指定できます。 パス文字列の先頭にスラッシュ (\) を入力しないでください。 </p> <p>例：Set A と Set B の共通ワークスペースは、 <span class="filepath"> レポート\共通 </span> フォルダーを作成し、 <span class="filepath"> Report.cfg </span> 異なる生成および配信設定を持つ 2 つの異なるレポートセット用のファイル 両方 <span class="filepath"> Report.cfg </span> ファイルの場合、Workspace Path パラメーターは <i>プロファイル名</i>\Reports\Common。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> XSL 出力ファイル </td>
   <td colname="col2"> <i>オプション</i>。作成時に <span class="wintitle"> XSL テンプレート </span> がレポートインデックスに適用されます。 </td>
  </tr>
  <tr>
   <td colname="col1"> XSL テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>。レポートインデックスに適用する XSL テンプレートファイルのパス。 結果として変換された <span class="filepath"> .xml </span> 指定した <span class="wintitle"> XSL 出力ファイル </span>. 詳しくは、 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> レポートサンプルファイル </a> を参照してください。 </p> <p> <p>注意：以下を使用しない限り、 <span class="filepath"> .xsl </span> テンプレートレポートを生成する際、すべてのレポートは添付ファイルとして電子メールで配信されます。 </p> </p> </td>
  </tr>
 </tbody>
</table>
