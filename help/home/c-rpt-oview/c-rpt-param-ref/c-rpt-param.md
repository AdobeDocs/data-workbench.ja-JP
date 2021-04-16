---
description: Report.cfgパラメーターに関する情報です。
title: Report.cfg のパラメーター
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2350'
ht-degree: 4%

---

# Report.cfg のパラメーター{#report-cfg-parameters}

Report.cfgパラメーターに関する情報です。

[レポートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)に示すサンプル[!DNL Report.cfg]には、デフォルトで[!DNL Report.cfg]ファイルに含まれているパラメーターのみが含まれています。 次の表に、使用可能なすべての[!DNL Report.cfg]ファイルのパラメーターの説明を示します。

[!DNL Report.cfg]ファイルにパラメーターを追加する必要がある場合は、テキストエディターを使用して追加する必要があります。 そのための手順（各パラメーターエントリの定義方法の例を含む）については、[既存のReport.cfgファイルの編集](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)を参照してください。

>[!NOTE]
>
>次の表に示すパラメーターは、アルファベット順に一覧表示されています。 [!DNL Report.cfg]ファイルをData Workbenchで開くと、ベクトルはアルファベット順に表示され、続いて個々のパラメータがアルファベット順に表示されます。

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
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、指標インジケーターを含むレポートにのみ適用されます。 警告レポートを送信する前にワークシートに表示する必要がある指標の数。 </p> <p>指標インジケーターのワークシートで1つの指標のみが監視されている場合は、しきい値を1に設定します。 レポートは、シート内の指標が上向き/下向き矢印またはXに評価されるときに生成されます。レポートで複数の指標を監視する場合は、レポートの生成前に上向き/下向き矢印またはXに評価する必要がある指標の数を選択できます。 例えば、2つの指標が監視されている場合： 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">しきい値を1に設定すると、シート内の指標のいずれかが上向き/下向き矢印またはXに評価された場合に、レポートが生成されます。 </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">しきい値を2に設定した場合、両方の指標が上向き/下向き矢印またはXの値に評価されてからレポートが生成されます。 </li> 
     </ul> </p> <p>指標インジケーターの詳細については、『<i>Data Workbenchユーザーガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポートの再生成を許可 </td> 
   <td colname="col2"> <p><span class="keyword">レポートサーバー</span>が特定のレポートを作成または変更する際に、自動的に生成または再作成するかどうかを示します。 選択肢は true または false です。trueに設定した場合、レポートワークスペースを作成または変更すると、<span class="keyword">レポートサーバー</span>は、最新の実行のためにそのレポートを再生成します。 </p> <p> <p>注意： <span class="filepath"> Report.cfg </span>ファイルを変更すると、<span class="keyword">レポートサーバー</span>は、<span class="filepath"> Report.cfg </span>ファイルによって制御されるすべてのレポートを再生成します。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 添付ファイル </td> 
   <td colname="col2"> <p><i>オプション</i>. 電子メールで配信されるレポートと共に送信される添付ファイルの名前とコンテンツタイプを表すセクション識別子（添付ファイルの数など）。 </p> <p>新しい添付ファイルを追加するには： 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E"><span class="filepath"> Report.cfg </span>ファイルをData Workbenchーで開きます。 </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">「<span class="uicontrol">添付ファイル</span>」を右クリックし、「<span class="uicontrol"> 追加 new child </span> 」/「<span class="uicontrol">添付ファイル</span> 」をクリックします。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コンテンツタイプ </td> 
   <td colname="col2"> <p>添付するファイルのコンテンツタイプ。 </p> <p>例：image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> FileName </td> 
   <td colname="col2"> <p>添付するファイルの場所と名前。 </p> <p>例：<span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color Set </td> 
   <td colname="col2"> <span class="filepath"> .png </span>ファイルに使用するカラースキームを指定します。 0は黒の背景用、1は白の背景用です。と2はグレースケール画像用です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 実行するコマンド </td> 
   <td colname="col2"> <i>オプション</i>. レポートセットの生成後に実行されるバッチコマンドまたは実行可能ファイル。 コマンドシェルインタープリタの起動が必要な場合は、コマンドの前にcmd /cを付けます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 既定のExcelテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートをExcelファイルとして生成するときに使用する汎用Excelテンプレートファイル（<span class="filepath"> .xls </span>または<span class="filepath"> .xlsx </span>）のファイル名。 このパラメーターは、<span class="filepath"> c:\templates\mytemplate.xls </span>のような完全なファイルパスをサポートします。 </p> <p>テンプレートが特定のレポート専用に定義されていない場合、このファイルはすべてのExcelレポートで使用されます。 「<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">テンプレートファイルの使用</a>」を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ディメンション名 </td> 
   <td colname="col2"> <i>オプション</i>. レポートを動的に生成するディメンションの名前。 このパラメーターにディメンション名を入力する場合は、Lookup Fileパラメーター、またはTop N MetricパラメーターとTop N Valueパラメーターのいずれかに値を入力する必要があります。 このパラメーターに指定するディメンションは、レポートの作成対象となるデータセットに存在する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完全な場合のみ電子メール </td> 
   <td colname="col2"> <i>オプション</i>. ユーザーは、実行中にエラーが発生しなかった場合にのみレポートセットを送信するように指定できます。 選択肢は true と false です。デフォルト値は false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 終了日 </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートセットを実行する最後の日時。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYYY hh:mmタイムゾーン（時間の24時間構文を使用） </p> <p>例：08/01/2007 12:01 EDT </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 毎 </td> 
   <td colname="col2"> レポートセット生成の頻度：日、週または月。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excelウォッチドッグタイムアウト（秒） </td> 
   <td colname="col2"> <p><i>オプション</i>. <span class="keyword"> Report Server </span>がExcelファイルとしてレポートを生成する際に、<span class="keyword">レポートサーバー</span>がMicrosoft Excelの応答を待機する秒数です。この秒数を経過すると、Excelが応答しないと判断され、プロセスが終了します。 このパラメータを使用すると、<span class="keyword"> Report Server </span>は、応答しなくなったときにExcelを終了し、Excel以外のレポートの処理を続行できます。 デフォルト値は300.0です。この機能を無効にするには、このパラメーターを0.0に設定します。 </p> <p>定義した値がExcelにエクスポートできる長さであることを確認します。 それ以外の場合は、<span class="keyword">レポートサーバー</span>がExcelを途中で終了し、レポートは生成されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルターの数式 </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートセット内のすべてのワークスペースに適用されるフィルター。 </p> <p>詳しくは、フィルター作成の<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external">構文</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ガンマ補正 </td> 
   <td colname="col2"> <p><span class="filepath"> .png </span>ファイル出力のガンマ設定。 デフォルトは 1.6 です。 </p> <p> <p>注意： Adobeでは、この値を変更しないことをお勧めします。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ロゴの非表示 </td> 
   <td colname="col2"> レポートを生成する際に、Report Serverでロゴを非表示にするかどうかを指定します。 オプションは<span class="filepath"> true </span>または<span class="filepath"> false </span>です。 <span class="filepath"> false </span>に設定した場合、レポートはレポートのロゴを使用して生成されます。 初期設定は <span class="filepath">false</span> です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 参照ファイル </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターを入力すると、Report Serverは動的モードで実行され、Dimension名パラメーターで指定されたディメンションの各要素に関するレポートが生成されます。 このファイルには、2つのタブ区切り列（ヘッダー行なし）を含める必要があります。 </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">列1には、ディメンション要素のリストが含まれます。 </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">列2には、レポート受信者の電子メールアドレスが含まれます。 列1の特定の要素に関するレポートが、列2の同じ行にある電子メールアドレスに送信されます。 複数の電子メールアドレスを入力する場合は、コンマで区切ります（スペースは使用できません）。 レポートを電子メールで送信しない場合は、空欄でもかまいませんが、レポートが存在している必要があります。 </li> 
     </ul> </p> <p> <p>注意： このパラメーターに値を入力する場合は、Dimensionー名パラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 通知のみ </td> 
   <td colname="col2"> この<span class="wintitle">レポートサーバー</span>設定を使用すると、レポートの生成時に電子メールを送信するようにdata workbenchを設定できます。 この値を<span class="filepath"> true </span>に設定すると、レポートは送信されませんが、サブスクライブしたユーザーにレポートが生成されたことを知らせる電子メールが送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> メールレポート </td> 
   <td colname="col2"> <p>電子メールでレポートを配信するためのセクション識別子。 電子メールでレポートを配信するには、<span class="wintitle">メールレポート</span>エントリの次のパラメーターを設定します。 レポートセット内のすべてのレポートは、受信者パラメーターで指定された電子メールアドレスに1通のメッセージで電子メールで送信されます。 </p> <p> <p>注意： レポートサーバーは、少なくとも1つのレポートが生成された場合にのみ電子メールを送信します。 </p> </p> <p>レポートの電子メール送信を有効にするには、このエントリに対して少なくとも次のパラメーターを設定する必要があります。 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP Server </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">受信者 </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">送信者のアドレス </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">通知のみ </li> 
     </ul> </p> <p> <p>注意： レポートセットを再生成した後にレポートを電子メールで送信する方法については、<a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887">既存のReport.cfgファイルの編集</a>を参照してください。 </p> </p> <p>「通知のみ」の値は、5.4xおよび5.5xリリースで使用できます。 </p> <p>通知を受ける受信者の大量セット（20件以上）には、電子メール配信リストを使用することを強くお勧めします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ボディXSLテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. <span class="filepath"> reports.xml </span>ファイルに適用するXSLテンプレートファイルのパスです。 このパラメーターを使用すると、Report Serverは、レポートを添付ファイルではなく、配信済みの電子メール内で送信できます。 結果のテキストは、電子メールメッセージの本文として使用されます。 </p> <p>サンプルファイルについては、<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">レポートサンプルファイル</a>を参照してください。 </p> <p>XSLT (Extensible Stylesheet Language)の詳細については、<a href="http://www.w3.org/Style/XSL/" format="http" scope="external"> The Extensible Stylesheet Language Family </a>を参照してください。 </p> </td> 
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
   <td colname="col2"> （オプション）送信者の名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP Server </td> 
   <td colname="col2"> SMTPサーバーコンピューターのアドレス、および認証に必要なパスワードとユーザー名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 件名 </td> 
   <td colname="col2"> <i>オプション</i>. 送信する電子メールを説明する件名行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 通知のみ </td> 
   <td colname="col2"> バックグラウンドレポートの生成時に電子メールを送信するようにdata workbenchを設定できます。 この値をTrueに設定すると、レポートは送信されず、登録ユーザーをレポートの場所にリンクする電子メールが送信されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Root </td> 
   <td colname="col2"> <p><i>オプション</i>. 生成されたレポートセットの出力場所。 デフォルトは、Report Serverのインストールディレクトリ内の<i>&lt;プロファイル名&gt;</i>\Reportsフォルダーです。 </p> <p><span class="keyword">レポートサーバー</span>がレポートをポータルに出力するように設定するには、<span class="wintitle">出力ルート</span>をポータルに使用するWebサーバーのドキュメントルートに設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> プリロードクエリフィルタ </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、<span class="wintitle">トップDimension要素</span>レポートタイプにのみ適用されます。 </p> <p>レポートを生成する前に、上位N個のディメンションクエリを決定するために実行する必要がある要素に適用するフィルターの名前。 デフォルト値は<span class="wintitle"> Broken_Session_Filter </span>です。 <span class="wintitle">壊れたセッションフィルター</span>の詳細については、『<i>Data Workbenchユーザーガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> レポートタイプ </span> </td> 
   <td colname="col2"> <p>出力を生成する形式。 次のオプションのいずれかまたはすべてを使用して、複数の形式でレポートセットを一度に出力できます。 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excelでは、ワークシートごとに1つのビジュアライゼーションを持つExcelワークブックが作成されます。 原則として、電子メールの配信にはExcelファイルを使用します。 「<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> Microsoft Excelファイルとしてのレポートの生成</a> 」を参照してください。 テンプレートファイルの使用について詳しくは、<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">テンプレートファイルの使用</a>を参照してください。 </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">pngを指定すると、Portable Network Graphicファイルが作成されます。 一般的に、Webブラウザー（ポータル）での表示には、<span class="filepath"> .png </span>ファイルを使用します。 </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">サムネールは、ワークスペースのサムネール（<span class="filepath"> .jpg </span>ファイル）を作成します。 デフォルトサイズは240 x 180です。 初期設定のサイズを変更するには、Thumbnail XパラメーターとThumbnail Yパラメーターを編集します。 </li> 
     </ul> </p> <p>Data Workbenchで<span class="filepath"> Report.cfg </span>を編集する際に新しいレポートタイプを追加するには、<span class="uicontrol">レポートタイプ</span>を右クリックし、<span class="uicontrol">追加新しい子</span>をクリックして、目的のレポートタイプを選択します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始日 </td> 
   <td colname="col2"> <p>レポートセットを実行する最初の日時。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYY hh:mmタイムゾーン（24時間構文を使用）。 </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> <p> <p>注意： プロファイル内のデータのタイムスタンプが指定した日時と一致する場合に実行するレポート開始。 </p> </p> <p>例： </p> <p>開始日が米国東部標準時(EST)の08/08/08/2006 12:00の場合、レポートは米国東部標準時(EST)の08/08/2006 12:00以降のタイムスタンプを持つデータに対して実行されます。 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">日別レポートは2006年8月8日に実行され、その後、hh:mm = 12:00 ESTのデータに対して毎日実行されます。 </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">週別レポートは2006年8月8日に実行され、その後7日ごとにhh:mm = 12:00 ESTのデータが実行されます。 </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月別レポートは2006年8月8日、それ以降の月の8日間はhh:mm = 12:00 ESTのデータで実行されます。 </li> 
     </ul> </p> <p><span class="wintitle">レポート時間</span>指標は、「過去7日間」、「昨日」、「3週間前」など、「過去N」のレポートディメンションに影響します。 レポートサーバーのクエリの場合、<span class="wintitle">レポート時間</span>指標（ <span class="filepath">レポート時間.metric </span>）は、レポートが実行される日時を示します。 これは、最初は開始日パラメーターで指定された日時で、次にEveryパラメーターで指定された期間だけ増加します。 Data Workbenchのクエリの場合、<span class="wintitle">レポート時間</span>指標は、基準日指標（ <span class="filepath">基準日.metric </span> ）の午前0時に基づきます。 レポート時間指標の定義が異なるので、Last Nディメンションを使用するワークスペースをクエリする場合、data workbenchと同じワークスペースの<span class="keyword">レポートサーバー</span>で異なる結果を受け取ることができます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サムネールX </td> 
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールのX軸のサイズ（ピクセル単位）を制御する整数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> サムネールY </td> 
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールのY軸のサイズ（ピクセル単位）を制御する整数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上位N件の指標 </td> 
   <td colname="col2"> <p><i>オプション</i>. 上位N個の値パラメーターの説明を参照してください。 </p> <p> <p>注意： このパラメーターに値を入力する場合は、「Dimension名」パラメーターと「上位N個の値」パラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上位N値 </td> 
   <td colname="col2"> <p><i>オプション</i>. このパラメーターを入力すると、<span class="keyword">レポートサーバー</span>は動的モードで実行され、N個の指標パラメーターで指定された指標でカウントし、Dimension名パラメーターで指定されたディメンションの最上位の数値（このパラメーターで指定）のレポートを生成します。 </p> <p>例：Dimension名パラメーターに「ページ」、「上位N件の指標」パラメーターに「セッション」、このパラメーターに「5」と入力した場合、生成されるレポートでは、セッション数が最も多い上位5ページがリストされます。 </p> <p> <p>注意： このパラメーターに値を入力する場合は、Dimension名パラメーターと上位N件の指標パラメーターに値を入力する必要があります。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ローカルサンプルのみを使用 </td> 
   <td colname="col2"> <i>オプション</i>. <span class="keyword">レポートサーバー</span>で、データセットのローカルサンプルのみを使用してレポートを生成するかどうかを示します。 このパラメーターをtrueに設定すると、（data workbenchサーバーに読み込むことなく）レポートセットのサンプルを表示し、データの処理に要する時間をすべて費やさずに出力の見え方を確認できます。 これはテスト関数として機能します。 選択肢は true または false です。デフォルトは false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ワークスペースパス </td> 
   <td colname="col2"> <p><i>オプション</i>. 特定のレポートセットに対するワークスペースのコレクションの場所。 これは、複数のレポートセットに対して<span class="filepath"> Report.cfg </span>ファイルを使用し、複数の方法で生成および配布する必要があるワークスペースのコピーを1つに維持する場合に役立ちます。 このパスのルートディレクトリは、任意のプロファイルフォルダーにすることができます。 パス文字列の開始にスラッシュ(\)を入力しないでください。 </p> <p>例：セットAとセットBの共通ワークスペースを<span class="filepath"> Reports\Common </span>フォルダーに保存し、2つの異なるレポートセット用に<span class="filepath"> Report.cfg </span>ファイルを定義して、それぞれの生成と配布の設定を変更できます。 両方の<span class="filepath"> Report.cfg </span>ファイルで、Workspace Pathパラメーターを<i>プロファイル名</i>\Reports\Commonに設定します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL出力ファイル </td> 
   <td colname="col2"> <i>オプション</i>. <span class="wintitle"> XSLテンプレート</span>がレポートインデックスに適用されるときに作成される出力ファイルのパスです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSLテンプレート </td> 
   <td colname="col2"> <p><i>オプション</i>. レポートインデックスに適用するXSLテンプレートファイルのパスです。 変換結果の<span class="filepath"> .xml </span>は、指定された<span class="wintitle"> XSL出力ファイル</span>に書き込まれます。 サンプルファイルについては、<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">レポートサンプルファイル</a>を参照してください。 </p> <p> <p>注意： レポートの生成時に<span class="filepath"> .xsl </span>テンプレートを使用しない限り、すべてのレポートは添付ファイルとして電子メールで配信されます。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
