---
description: Report.cfgパラメーターに関する情報です。
solution: Analytics
title: Report.cfgのパラメーター
topic: Data workbench
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Report.cfgのパラメーター{#report-cfg-parameters}

Report.cfgパラメーターに関する情報です。

「レポートセ [!DNL Report.cfg] ットの設 [定」に示すサンプルには](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) 、デフォルトでファイルに含まれるパラメ [!DNL Report.cfg] ータのみが含まれます。 次の表に、使用可能なすべてのファイルパラメーターの説 [!DNL Report.cfg] 明を示します。

ファイルにパラメータを追加する必要がある場 [!DNL Report.cfg] 合は、テキストエディターを使用して追加する必要があります。 各パラメーターエントリの定義方法の例を含め、その手順については、既存のReport.cfgフ [ァイルの編集を参照してください](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

>[!NOTE]
>
>次の表に示すパラメータは、アルファベット順に一覧表示されています。 Data Workbenchでファイルを開く [!DNL Report.cfg] と、ベクトルがアルファベット順に表示され、その後に個々のパラメーターがアルファベット順に表示されます。

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
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、指標インジケーターを含むレポートにのみ適用されます。 警告レポートを送信する前にワークシートに表示する必要がある指標の数。 </p> <p>指標インジケーターのワークシートで1つの指標のみが監視されている場合は、しきい値を1に設定します。 シート内の指標が上向き/下向き矢印またはXに評価された場合、レポートが生成されます。レポート内で複数の指標が監視されている場合は、レポートが生成される前に上向き/下向き矢印またはXに評価する必要がある指標の数を選択できます。 例えば、2つの指標が監視されている場合： 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">しきい値を1に設定すると、シート内の指標のいずれかが上向き/下向き矢印またはXに評価された場合に、レポートが生成されます。 </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">しきい値を2に設定した場合、両方の指標が上向き/下向き矢印またはXに評価されてから、レポートが生成されます。 </li> 
     </ul> </p> <p>For more information about metric indicators, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポートの再生成を許可 </td> 
   <td colname="col2"> <p>レポートを作成ま <span class="keyword"> たは変 </span> 更する際に、Report Serverが特定のレポートを自動的に生成または再生成するかどうかを示します。 選択肢は true または false です。trueに設定した場合、レポートワークスペースを作成または変更すると、 <span class="keyword"> Report Serverは最新の実 </span> 行時にそのレポートを再生成します。 </p> <p> <p>注意： Report.cfgファイルを変 <span class="filepath"> 更すると、Report Serverは </span> そのReport.cfgフ <span class="keyword"> ァイルで制御されるすべてのレ </span> ポートを再生成し <span class="filepath"></span> ます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 添付ファイル </td> 
   <td colname="col2"> <p><i>オプション</i>. 電子メールで配信されるレポートで送信される添付ファイルの名前とコンテンツタイプを表すセクション識別子（添付ファイルの数を含む）。 </p> <p>新しい添付ファイルを追加するには： 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">Data Workbenchで <span class="filepath"> Report.cfgフ </span> ァイルを開きます。 </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">Attachmentsを右クリックし、 <span class="uicontrol"> 新しい子を追 </span> 加/ <span class="uicontrol"> Attachmentをク </span> リック <span class="uicontrol"> しま </span>す。 </li> 
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
   <td colname="col2"> .pngファイルに使用するカラースキームを <span class="filepath"> 指定し </span> ます。 0は黒の背景用、1は白の背景用、と2はグレースケール画像用です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 実行するコマンド </td> 
   <td colname="col2"> <i>オプション</i>. レポートセットの生成後に実行されるバッチコマンドまたは実行可能ファイル。 コマンドシェルインタープリタの起動が必要な場合は、コマンドの前にcmd /cを付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 既定のExcelテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートをExcelファイルとして生成する際に使用する汎用Excelテ <span class="filepath"> ンプレートファイル(.xlsま </span> たは.xlsx <span class="filepath"></span>)のファイル名です。 このパラメーターは、c:\templates\mytemplate.xlsなどの完全なファイルパスをサポート <span class="filepath"> していま </span>す。 </p> <p>このファイルは、特定のレポート用にテンプレートが定義されていない限り、すべてのExcelレポートで使用されます。 詳しくは、テ <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> ンプレートファイルの使用を参照してくだ </a>さい。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ディメンション名 </td> 
   <td colname="col2"> <i>オプション</i>. レポートを動的に生成するディメンションの名前。 このパラメーターにディメンション名を入力する場合は、Lookup Fileパラメーター、またはTop N MetricパラメーターとTop N Valueパラメーターのいずれかに値を入力する必要があります。 このパラメーターで指定するディメンションは、レポートを作成するデータセットに存在する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完全な場合のみ電子メールを送信 </td> 
   <td colname="col2"> <i>オプション</i>. 実行中にエラーが発生しなかった場合にのみレポートセットを送信するようにユーザーが指定できます。 選択肢は true と false です。デフォルト値は false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 終了日 </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートセットを実行する最後の日時。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYYY hh:mmタイムゾーン。24時間構文を使用 </p> <p>例：08/01/2007 12:01 EDT </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 毎 </td> 
   <td colname="col2"> レポートセットの生成の頻度：日、週または月。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excelウォッチドッグタイムアウト（秒） </td> 
   <td colname="col2"> <p><i>オプション</i>. Excelファイルとしてレポートを生成する際に、Excelが応答しないとReport Serverが判断してプロセスを終了するま <span class="keyword"> での、Microsoft Excelの応答をReport Serverが待機する </span><span class="keyword"></span> 秒数です。 このパラメータを使用すると、 <span class="keyword"> Excelが応答しな </span> くなった場合にExcelを終了し、Excel以外のレポートの処理を続行できます。 デフォルトは300.0です。この機能を無効にするには、このパラメーターを0.0に設定します。 </p> <p>定義した値がExcelにエクスポートできる長さであることを確認します。 そうしないと、 <span class="keyword"> Report Serverが早 </span> 期にExcelを終了し、レポートが生成されない場合があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルター式 </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートセット内のすべてのワークスペースに適用されるフィルター。 </p> <p>詳しくは、フィルター作成の構文 <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> を参照してくださ </a>い。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ガンマ補正 </td> 
   <td colname="col2"> <p>.pngファイル出力 <span class="filepath"> のガンマ </span> 設定。 デフォルトは 1.6 です。 </p> <p> <p>注意： この値は変更しないことをお勧めします。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ロゴを隠す </td> 
   <td colname="col2"> レポートを生成する際に、Report Serverでロゴを非表示にするかどうかを指定します。 The options are <span class="filepath"> true </span> or <span class="filepath"> false </span>. falseに設定した場 <span class="filepath"> 合、レ </span>ポートはレポートのロゴと共に生成されます。 初期設定は <span class="filepath">false</span> です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照ファイル </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターを入力すると、Report Serverは動的モードで実行され、Dimension Nameパラメーターで指定されたディメンションの各要素に関するレポートが生成されます。 このファイルには、2つのタブ区切り列（ヘッダー行なし）が含まれている必要があります。 </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">列1には、ディメンション要素のリストが含まれます。 </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">列2には、レポートの受信者の電子メールアドレスが含まれます。 列1の特定の要素に関するレポートが、列2の同じ行の電子メールアドレスに送信されます。 複数の電子メールアドレスを入力する場合は、コンマ（スペースなし）で区切ります。 レポートを電子メールで送信しない場合は、この列を空にすることができますが、存在している必要があります。 </li> 
     </ul> </p> <p> <p>注意： このパラメーターに値を入力する場合は、Dimension Nameパラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 通知のみ </td> 
   <td colname="col2"> このレポ <span class="wintitle"> ートサ </span> ーバー設定を使用すると、レポートの生成時に電子メールを送信するようにData Workbenchを設定できます。 この値をtrueに設定すると、レ <span class="filepath"> ポー </span> トは送信されず、登録ユーザーに対してレポートが生成されたことを知らせる電子メールが送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> メールレポート </td> 
   <td colname="col2"> <p>レポートを電子メールで配信するためのセクション識別子。 レポートを電子メールで配信するには、「電子メールレポート」エントリの次のパ <span class="wintitle"> ラメータを入力 </span> します。 レポートセット内のすべてのレポートは、Recipientsパラメーターで指定された電子メールアドレス宛てに1つのメッセージで送信されます。 </p> <p> <p>注意： レポートサーバーは、少なくとも1つのレポートが生成された場合にのみ電子メールを送信します。 </p> </p> <p>レポートの電子メール送信を有効にするには、このエントリに対して少なくとも次のパラメーターを設定する必要があります。 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP Server </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">受信者 </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">送信者のアドレス </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">通知のみ </li> 
     </ul> </p> <p> <p>注意： レポートセットを再生成した後にレポートを電子メールで送信する方法については、既存のReport.cfgフ <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> ァイルの編集を参照してくださ </a>い。 </p> </p> <p>「通知のみ」の値は、5.4xおよび5.5xリリースで使用できます。 </p> <p>多数の受信者に通知を送信する場合（20人以上）は、電子メールの配信リストを使用することを強くお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ボディXSLテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. reports.xmlファイルに適用するXSLテンプレートフ <span class="filepath"> ァイルのパ </span> ス。 このパラメーターを使用すると、Report Serverは、レポートを添付ファイルではなく、配信済みの電子メール内で送信できます。 結果のテキストは、電子メールメッセージの本文として使用されます。 </p> <p>サンプルファ <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> イルについては、レポ </a> ートのサンプルファイルを参照してください。 </p> <p>XSLT(Extensible Stylesheet Language)の詳細については、『The Extensible Stylesheet Language Family』を <a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> 参照してください </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 受信者 </td> 
   <td colname="col2"> レポートの送信先の人の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信者のアドレス </td> 
   <td colname="col2"> 送信者の電子メールアドレス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 送信者名 </td> 
   <td colname="col2"> (オプション)送信者の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server </td> 
   <td colname="col2"> SMTPサーバーコンピューターのアドレスと、認証に必要なパスワードとユーザー名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 件名 </td> 
   <td colname="col2"> <i>オプション</i>. 送信する電子メールの件名行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 通知のみ </td> 
   <td colname="col2"> バックグラウンドレポートの生成時に電子メールを送信するようにData Workbenchを設定できます。 この値をTrueに設定すると、レポートは送信されず、登録ユーザーをレポートの場所にリンクする電子メールが送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出力ルート </td> 
   <td colname="col2"> <p><i>オプション</i>. 生成されたレポートセットの出力場所。 デフォルトは、Report Serverのイ <i>ンストールディレクトリ</i>内の&lt;profile name&gt;\Reportsフォルダーです。 </p> <p>レポートをポー <span class="keyword"> タルに </span> 出力するようにReport Serverを設定するには、Output Rootをポータルに使用するWebサーバーのドキ <span class="wintitle"></span> ュメントルートに設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プリロードクエリフィルタ </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、上位のディメンション <span class="wintitle"> 要素レポートタイ </span> プにのみ適用されます。 </p> <p>レポートを生成する前に、上位N個のディメンション要素を決定するために実行する必要があるクエリーに適用するフィルターの名前。 デフォルトは <span class="wintitle"> Broken_Session_Filterです </span>。 For more information about the <span class="wintitle"> Broken Session Filter </span>, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> レポートタイプ </span> </td> 
   <td colname="col2"> <p>出力を生成する形式。 次のオプションのいずれかまたはすべてを使用して、複数の形式でレポートセットを一度に出力できます。 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excelでは、ワークシートごとに1つのビジュアライゼーションを持つExcelワークブックが作成されます。 一般的に、電子メールの配信にはExcelファイルを使用します。 「Microsoft Excelファ <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> イルとしてのレポートの生成」を参照してくださ </a>い。 テンプレートファイルの使用に関する詳細は、「テンプレートファ <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> イルの使用」を参照してくださ </a>い。 </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">pngを指定すると、Portable Network Graphicファイルが作成されます。 一般的に、Webブラウザー（ポータル） <span class="filepath"> に表 </span> 示する.pngファイルを使用します。 </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">サムネールは、ワークスペースのサ <span class="filepath"> ムネール(.jpg </span> ファイル)を作成します。 デフォルトのサイズは240 x 180です。 初期設定のサイズを変更するには、「サムネールX」と「サムネールY」の各パラメーターを編集します。 </li> 
     </ul> </p> <p>Data Workbenchで <span class="filepath"> Report.cfgを編集する際に新しいレポートタイプを追加するには、「レポートタイプ」を右クリックし、「新しい子を追加」をクリックし </span> て、 <span class="uicontrol"> 目的のレポートタイプ </span><span class="uicontrol"></span>を選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始日 </td> 
   <td colname="col2"> <p>レポートセットを実行する最初の日時。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYY hh:mmタイムゾーン。24時間構文を使用。 </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> <p> <p>注意： プロファイル内のデータのタイムスタンプが指定した日時と一致すると、レポートの実行が開始されます。 </p> </p> <p>例： </p> <p>開始日が2006年8月8日12:00 ESTの場合、レポートは米国東部標準時(EST)のタイムスタンプが08/08/2006年12:00以降のデータに対して実行されます。 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">日別レポートは2006年8月8日に実行され、その後、hh:mm = 12:00 ESTのデータに対して毎日実行されます。 </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">週別レポートは、2006年8月8日と、その後7日ごとにhh:mm = 12:00 ESTのデータに対して実行されます。 </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月別レポートは、hh:mm = 12:00 ESTのデータに対して、2006年8月8日とそれ以降の月の8日に対して実行されます。 </li> 
     </ul> </p> <p>レポ <span class="wintitle"> ート時 </span> 間指標は、「過去7日間」、「昨日」、「3週間前」など、「過去N」のレポートディメンションに影響します。レポートサーバーのクエリ <span class="wintitle"> ーの場合、レ </span> ポート時間指標( <span class="filepath"> Report Time.metric </span>)は、レポートが実行される日時を識別します。 これは、Start Dateパラメーターで指定された日時で、Everyパラメーターで指定された期間だけ増分されます。 Data Workbenchのクエリーの場合、レポ <span class="wintitle"> ート時 </span> 間指標は基準日指標(基準日。指標 <span class="filepath"> )の深夜0時に基づ </span>いています。 レポート時間指標の定義が異なるので、Last Nディメンションを使用するワークスペースをクエリーする場合、同じワークスペースに対して、Data Workbenchと <span class="keyword"> Report Serverで異なる結果を受け取るこ </span> とができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サムネールX </td> 
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールのX軸のサイズ（ピクセル単位）を制御する整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サムネールY </td> 
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールのY軸のサイズ（ピクセル単位）を制御する整数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上位N件の指標 </td> 
   <td colname="col2"> <p><i>オプション</i>. 上位N個の値パラメーターの説明を参照してください。 </p> <p> <p>注意： このパラメーターに値を入力する場合は、ディメンション名パラメーターと上位N個の値パラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上位N値 </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターを入力すると、 <span class="keyword"></span> Report Serverは動的モードで実行され、Dimension Nameパラメーターで指定されたディメンションのエレメントの上位の数（このパラメーターで指定）に関するレポートが生成されます。この数値は、Top N指標パラメーターで指定された指標でカウントされます。 </p> <p>例：ディメンション名パラメーターに「ページ」、「上位N件の指標」パラメーターに「セッション」、このパラメーターに「5」と入力した場合、生成されるレポートには、セッション数が最も多い上位5つのページが表示されます。 </p> <p> <p>注意： このパラメーターに値を入力する場合は、Dimension NameパラメーターとTop N指標パラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ローカルサンプルのみを使用 </td> 
   <td colname="col2"> <i>オプション</i>. データセットのローカルサ <span class="keyword"> ンプルの </span> みを使用してレポートをReport Serverで生成するかどうかを示します。 このパラメーターをtrueに設定すると、レポートセットのサンプル（Data Workbenchサーバーに読み込むことなく）を表示し、データを完全に処理するのに必要な時間をかけずに、出力の見え方を確認できます。 これはテスト関数として機能します。 選択肢は true または false です。デフォルトは false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ワークスペースパス </td> 
   <td colname="col2"> <p><i>オプション</i>. 特定のレポートセットのワークスペースのコレクションの場所。 これは、複数のレポートセットに対して <span class="filepath"> Report.cfgファイルを使用して、複数の方法で生成および配布する必要があるワークスペースの1つのコピーを保 </span> 持する場合に役立ちます。 このパスのルートディレクトリは、任意のプロファイルフォルダーにすることができます。 パス文字列の先頭にはスラッシュ(\)を入力しないでください。 </p> <p>例：セットAとセットBの共通のワークスペースを <span class="filepath"> Reports\Commonフォルダーに保存し、2つの異なるレポートセットに対して </span> Report.cfg <span class="filepath"></span> ファイルを定義し、それぞれ異なる生成と配信の設定を行うことができます。 両方の <span class="filepath"> Report.cfgフ </span> ァイルで、Workspace Pathパラメーターをprofile <i>name \Reports\Commonに設定し</i>ます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL出力ファイル </td> 
   <td colname="col2"> <i>オプション</i>. XSLテンプレートがレポートインデックスに適用され <span class="wintitle"> たときに作 </span> 成される出力ファイルのパス。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSLテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートインデックスに適用するXSLテンプレートファイルのパス。 変換後の <span class="filepath"> .xmlは、指 </span> 定した <span class="wintitle"> XSL出力ファイルに書き込まれます </span>。 サンプルファ <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> イルについては、レポ </a> ートのサンプルファイルを参照してください。 </p> <p> <p>注意： レポートの生成時に <span class="filepath"> .xslテン </span> プレートを使用しない限り、すべてのレポートは添付ファイルとして電子メールで配信されます。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

