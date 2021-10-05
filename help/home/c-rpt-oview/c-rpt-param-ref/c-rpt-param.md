---
description: Report.cfg パラメーターについて取り上げます。
title: Report.cfg のパラメーター
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 4%

---

# Report.cfg のパラメーター{#report-cfg-parameters}

Report.cfg パラメーターについて取り上げます。

[ レポートセットの設定 ](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) に示すサンプル [!DNL Report.cfg] には、デフォルトで [!DNL Report.cfg] ファイルに含まれているパラメーターのみが含まれています。 次の表に、使用可能な [!DNL Report.cfg] ファイルのパラメータの説明を示します。

[!DNL Report.cfg] ファイルにパラメータを追加する必要がある場合は、テキストエディタを使用して追加する必要があります。 各パラメーターエントリの定義方法の例を含め、指定する手順については、[ 既存の Report.cfg ファイルの編集 ](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887) を参照してください。

>[!NOTE]
>
>この表のパラメータは、アルファベット順にリストされます。 [!DNL Report.cfg] ファイルをData Workbenchで開くと、ベクトルがアルファベット順に並べられ、その後に個々のパラメータがアルファベット順に並べられます。

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
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、指標インジケーターを含むレポートにのみ適用されます。 警告レポートを送信する前にワークシートに表示する必要がある指標の数。 </p> <p>指標インジケーターのワークシートで 1 つの指標のみが監視されている場合は、しきい値を 1 に設定します。 レポートは、シート内の指標が上下矢印または X に評価されると生成されます。レポートで複数の指標が監視されている場合は、レポートが生成される前に上下矢印または X に評価する必要がある指標の数を選択できます。 例えば、2 つの指標が監視されている場合：
     <ul id="ul_A64E8A2306B14371A233D372B956F64D">
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">しきい値を 1 に設定すると、シート内の指標のいずれかが上向き/下向き矢印または X に評価された場合に、レポートが生成されます。 </li>
      <li id="li_DA4EF4984880483DA48322D9D57B9240">しきい値を 2 に設定した場合、レポートが生成される前に、両方の指標が上向き/下向き矢印または X に評価される必要があります。 </li>
     </ul> </p> <p>指標の詳細については、『<i>Data Workbenchユーザーガイド </i>』を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> レポートの再生成を許可 </td>
   <td colname="col2"> <p><span class="keyword"> レポートサーバー </span> で特定のレポートを作成または変更する際に、特定のレポートを自動的に生成または再生成するかどうかを示します。 選択肢は true または false です。true に設定した場合、レポートワークスペースを作成または変更すると、<span class="keyword"> レポートサーバー </span> は最新の実行でそのレポートを再生成します。 </p> <p> <p>注意： <span class="filepath"> Report.cfg </span> ファイルを変更すると、<span class="keyword"> レポートサーバー </span> は、その <span class="filepath"> Report.cfg </span> ファイルによって制御されるすべてのレポートを再生成します。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 添付ファイル </td>
   <td colname="col2"> <p><i>オプション</i>. 電子メールで配信されたレポートで送信される添付ファイルの名前とコンテンツタイプ（添付ファイルの数を含む）のセクション識別子。 </p> <p>新しい添付ファイルを追加するには：
     <ol id="ol_CBDC1E95D34A4D08A862680127438433">
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E"><span class="filepath"> Report.cfg </span> ファイルをData Workbenchで開きます。 </li>
      <li id="li_0709ADDDDF2E469FAB10761B46173136"><span class="uicontrol"> 添付ファイル </span> を右クリックし、<span class="uicontrol"> 新しい子の追加 </span> / <span class="uicontrol"> 添付ファイル </span> をクリックします。 </li>
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
   <td colname="col2"> <span class="filepath"> .png </span> ファイルに使用するカラースキームを指定します。 0 は黒の背景用、1 は白の背景用、2 はグレースケール画像用です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 実行するコマンド </td>
   <td colname="col2"> <i>オプション</i>. レポートセットの生成後に実行されるバッチコマンドまたは実行可能ファイル。 コマンドシェルインタプリタの起動が必要な場合は、コマンドの前に cmd /c を付けます。 </td>
  </tr>
  <tr>
   <td colname="col1"> 既定の Excel テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>. レポートを Excel ファイルとして生成する際に使用する汎用の Excel テンプレートファイル（ <span class="filepath"> .xls </span> または <span class="filepath"> .xlsx </span> ）のファイル名。 このパラメーターは、完全なファイルパス ( 例： <span class="filepath"> c:\templates\mytemplate.xls </span> ) をサポートします。 </p> <p>このファイルは、特定のレポート用にテンプレートが定義されていない限り、すべての Excel レポートで使用されます。 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> テンプレートファイルの使用 </a> を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ディメンション名 </td>
   <td colname="col2"> <i>オプション</i>. レポートを動的に生成するディメンションの名前。 このパラメーターにディメンション名を入力する場合は、「参照ファイル」パラメーター、または「上位 N 件の指標」パラメーターと「上位 N 件の値」パラメーターのいずれかに値を入力する必要があります。 このパラメーターで指定するディメンションは、レポートの作成対象となるデータセット内に存在する必要があります。 </td>
  </tr>
  <tr>
   <td colname="col1"> 完全な場合のみ電子メール </td>
   <td colname="col2"> <i>オプション</i>. 実行中にエラーが発生しなかった場合にのみレポートセットを送信するようにユーザーが指定できます。 選択肢は true と false です。デフォルト値は false です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 終了日 </td>
   <td colname="col2"> <p><i>オプション</i>. レポートセットを実行する最後の日時。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYYY hh:mm タイムゾーン（時刻の 24 時間構文を使用） </p> <p>例：08/01/2007 12:01 EDT </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 毎 </td>
   <td colname="col2"> レポートセット生成の頻度：日、週、月 </td>
  </tr>
  <tr>
   <td colname="col1"> Excel ウォッチドッグのタイムアウト（秒） </td>
   <td colname="col2"> <p><i>オプション</i>. Excel ファイルとしてレポートを生成する際に、<span class="keyword"> Report Server </span> がMicrosoft Excel の応答を待機する秒数です。この秒数を過ぎると、<span class="keyword"> Report Server </span> は Excel が応答しないと判断し、プロセスを終了します。 このパラメーターを使用すると、<span class="keyword"> Report Server </span> は応答しなくなり、Excel 以外のレポートの処理を続行したときに Excel を終了できます。 デフォルト値は 300.0 です。この機能を無効にするには、このパラメーターを 0.0 に設定します。 </p> <p>定義した値が、レポートを Excel にエクスポートできるだけの長さであることを確認します。 そうしないと、<span class="keyword"> Report Server </span> が Excel を途中で終了し、レポートが生成されない場合があります。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> フィルター式 </td>
   <td colname="col2"> <p><i>オプション</i>. レポートセット内のすべてのワークスペースに適用されるフィルター。 </p> <p>詳しくは、<a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> フィルターを作成するための構文 </a> を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ガンマ補正 </td>
   <td colname="col2"> <p><span class="filepath"> .png </span> ファイル出力のガンマ設定。 デフォルトは 1.6 です。 </p> <p> <p>注意： Adobeでは、この値を変更しないことをお勧めします。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ロゴを隠す </td>
   <td colname="col2"> レポートの生成時に、レポートサーバーでロゴを非表示にするかどうかを示します。 オプションは <span class="filepath"> true </span> または <span class="filepath"> false </span> です。 <span class="filepath"> false </span> に設定した場合、レポートはレポートのロゴを使用して生成されます。 初期設定は <span class="filepath">false</span> です。 </td>
  </tr>
  <tr>
   <td colname="col1"> 参照ファイル </td>
   <td colname="col2"> <p><i>オプション</i>. このパラメーターを入力すると、レポートサーバーは動的モードで実行され、Dimension名パラメーターで指定されたディメンションの各要素に関するレポートを生成します。 このファイルには、ヘッダー行のない、タブ区切りの 2 つの列が含まれている必要があります。 </p> <p>
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A">
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">列 1 には、次元要素のリストが含まれます。 </li>
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">列 2 には、レポートの受信者の電子メールアドレスが含まれます。 列 1 の特定の要素に関するレポートは、列 2 の同じ行にある E メールアドレスに送信されます。 複数の電子メールアドレスを入力する場合は、コンマ（スペースなし）で区切ります。 レポートを電子メールで送信しない場合、この列は空のままでもかまいませんが、存在する必要があります。 </li>
     </ul> </p> <p> <p>注意： このパラメータに値を入力する場合は、[Dimension名 ] パラメータに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 通知のみ </td>
   <td colname="col2"> この <span class="wintitle"> レポートサーバー </span> 設定を使用すると、レポートの生成時に電子メールを送信するように Data Workbench を設定できます。 この値を <span class="filepath"> true </span> に設定すると、レポートは送信されず、サブスクライブされたユーザーにレポートが生成されたことを知らせる電子メールが送信されます。 </td>
  </tr>
  <tr>
   <td colname="col1"> メールレポート </td>
   <td colname="col2"> <p>電子メールでレポートを配信するためのセクション識別子。 電子メールでレポートを配布するには、<span class="wintitle"> メールレポート </span> エントリの次のパラメーターを設定します。 レポートセット内のすべてのレポートは、「受信者」パラメーターで指定された電子メールアドレス宛に、1 つのメッセージで電子メールで送信されます。 </p> <p> <p>注意： レポートサーバーは、1 つ以上のレポートが生成された場合にのみ電子メールを送信します。 </p> </p> <p>レポートの電子メール送信を有効にするには、このエントリに対して少なくとも次のパラメーターを入力する必要があります。
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8">
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP Server </li>
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">受信者 </li>
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">送信者のアドレス </li>
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">通知のみ </li>
     </ul> </p> <p> <p>注意： レポートセットを再生成した後に電子メールでレポートを送信する方法については、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> 既存の Report.cfg ファイルの編集 </a> を参照してください。 </p> </p> <p>「通知のみ」の値は、5.4x および 5.5x リリースで使用できます。 </p> <p>多数の受信者に通知を送信する場合（20 人以上）は、E メール配布リストを使用することを強くお勧めします。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ボディ XSL テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>. <span class="filepath"> reports.xml </span> ファイルに適用する XSL テンプレートファイルのパス。 このパラメーターを使用すると、Report Server は、配信された電子メール内で、添付ファイルではなくレポートを送信できます。 結果のテキストは、E メールメッセージの本文として使用されます。 </p> <p>サンプルファイルについては、「 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> レポートサンプルファイル </a> 」を参照してください。 </p> <p>XSLT(Extensible Stylesheet Language) の詳細については、 <a href="https://www.w3.org/Style/XSL/" format="http" scope="external"> The Extensible Stylesheet Language Family </a> を参照してください。 </p> </td>
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
   <td colname="col2"> （オプション。送信者の名前。 </td>
  </tr>
  <tr>
   <td colname="col1"> SMTP Server </td>
   <td colname="col2"> SMTP サーバーマシンのアドレスと、認証に必要なパスワードとユーザー名。 </td>
  </tr>
  <tr>
   <td colname="col1"> 件名 </td>
   <td colname="col2"> <i>オプション</i>. 送信する E メールを説明する件名行。 </td>
  </tr>
  <tr>
   <td colname="col1"> 通知のみ </td>
   <td colname="col2"> バックグラウンドレポートの生成時に電子メールを送信するように Data Workbench を設定できます。 この値を True に設定すると、レポートは送信されず、購読ユーザーをリンクする電子メールがレポートの場所に送信されます。 </td>
  </tr>
  <tr>
   <td colname="col1"> 出力ルート </td>
   <td colname="col2"> <p><i>オプション</i>. 生成されたレポートセットの出力場所。 デフォルトは、Report Server のインストールディレクトリ内の <i>&lt;profile name&gt;</i>\Reports フォルダーです。 </p> <p><span class="keyword"> レポートサーバー </span> をポータルにレポートを出力するように設定するには、<span class="wintitle"> 出力ルート </span> を、ポータルに使用する Web サーバーのドキュメントルートに設定します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> プリロードクエリフィルター </td>
   <td colname="col2"> <p><i>オプション</i>. このパラメーターは、<span class="wintitle"> 上位のDimension要素 </span> レポートタイプにのみ適用されます。 </p> <p>レポートを生成する前に、上位 N 個のディメンション要素を決定するために実行する必要があるクエリに適用するフィルターの名前。 デフォルトは <span class="wintitle"> Broken_Session_Filter </span> です。 <span class="wintitle"> Broken Session Filter </span> の詳細については、<i>Data Workbenchユーザーガイド </i> を参照してください。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <span class="wintitle"> レポートタイプ </span> </td>
   <td colname="col2"> <p>出力を生成する形式。 次のオプションを使用して、複数の形式でレポートセットを一度に出力できます。
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9">
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel では、ワークシートごとに 1 つのビジュアライゼーションを持つ Excel ブックが作成されます。 原則として、Excel ファイルを電子メールの配信に使用します。 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee">Microsoft Excel ファイルとしてのレポートの生成 </a> を参照してください。 テンプレートファイルの使用については、 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> テンプレートファイルの使用 </a> を参照してください。 </li>
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png は Portable Network Graphic ファイルを作成します。 原則として、 <span class="filepath"> .png </span> ファイルを Web ブラウザー（ポータル）で表示する場合に使用します。 </li>
      <li id="li_869DA266E6A041A5BD343537743FAC79">サムネールは、ワークスペースのサムネール（ <span class="filepath"> .jpg </span> ファイル）を作成します。 デフォルトのサイズは 240 x 180 です。 デフォルトのサイズを変更するには、「サムネール X」および「サムネール Y」パラメーターを編集します。 </li>
     </ul> </p> <p>Data Workbench で <span class="filepath"> Report.cfg </span> を編集する際に新しいレポートタイプを追加するには、<span class="uicontrol"> レポートタイプ </span> を右クリックし、「<span class="uicontrol"> 新しい子 </span> を追加」をクリックして、目的のレポートタイプを選択します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 開始日 </td>
   <td colname="col2"> <p>レポートセットを実行する最初の日時です。 今回は、データセットの基準日時に基づきます。 </p> <p>形式：MM/DD/YYY hh:mm タイムゾーン（時刻の 24 時間構文を使用） </p> <p>タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> <p> <p>注意： プロファイル内のデータのタイムスタンプが指定した日時と一致すると、レポートの実行が開始されます。 </p> </p> <p>例： </p> <p>開始日が08/08/2006 12:00 EST の場合、タイムスタンプが08/08/2006 12:00 EST 以降のデータに対してレポートが実行されます。
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1">
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">日別レポートは08/08/2006で実行され、その後は日別に hh:mm = 12:00 EST のデータが表示されます。 </li>
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">週別レポートは08/08/2006で、その後 7 日ごとに hh:mm = 12:00 EST のデータで実行されます。 </li>
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">月別レポートは08/08/2006で、その後は毎月 8 日に hh:mm = 12:00 EST のデータで実行されます。 </li>
     </ul> </p> <p><span class="wintitle"> レポート時間 </span> 指標は、「過去 7 日間」、「昨日」、「3 週間前」など、「最近の N」のレポートディメンションに影響します。 レポートサーバーのクエリの場合、 <span class="wintitle"> レポート時間 </span> 指標（ <span class="filepath"> レポート時間.metric </span> ）は、レポートが実行される日時を示します。 最初は、Start Date パラメーターで指定された日時で、Every パラメーターで指定された期間だけ増分されます。 Data Workbench のクエリの場合、 <span class="wintitle"> レポート時間 </span> 指標は、基準日指標（ <span class="filepath"> 基準日.metric </span> ）の午前 0 時に基づきます。 レポート時間指標の定義の違いにより、Last N ディメンションを使用するワークスペースをクエリすると、同じワークスペースに対して Data Workbench と <span class="keyword"> レポートサーバー </span> で異なる結果を受け取ることができます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> サムネール X </td>
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールの X 軸のサイズ（ピクセル単位）を制御する整数。 </td>
  </tr>
  <tr>
   <td colname="col1"> サムネール Y </td>
   <td colname="col2"> <i>オプション</i>. 出力として生成されるサムネールの Y 軸のサイズ（ピクセル単位）を制御する整数。 </td>
  </tr>
  <tr>
   <td colname="col1"> 上位 N 指標 </td>
   <td colname="col2"> <p><i>オプション</i>. Top N Value パラメータの説明を参照してください。 </p> <p> <p>注意： このパラメータに値を入力する場合は、[Dimension名 ] パラメータと [ 上位 N 値 ] パラメータに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 上位 N 値 </td>
   <td colname="col2"> <p><i>オプション</i>. このパラメーターが入力されると、<span class="keyword"> レポートサーバー </span> は動的モードで実行され、「Dimension名」パラメーターで指定したディメンションの要素の上位の数（このパラメーターで指定）のレポートを生成します。 </p> <p>例：Dimension名パラメーターに「Page」、「Top N Metric」パラメーターに「Sessions」、このパラメーターに「5」と入力した場合、生成されるレポートには、セッション数が最も多い上位 5 ページが表示されます。 </p> <p> <p>注意： このパラメーターに値を入力する場合は、「Dimension名」パラメーターと「上位 N 件の指標」パラメーターに値を入力する必要があります。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ローカルサンプルのみを使用 </td>
   <td colname="col2"> <i>オプション</i>. <span class="keyword"> レポートサーバー </span> で、データセットのローカルサンプルのみを使用してレポートを生成するかどうかを示します。 このパラメーターを true に設定すると、レポートセットのサンプルを（Data Workbench サーバーに負荷をかけずに）表示して、データを完全に処理するのに必要な時間をかけずに、出力の見え方を確認できます。 これはテスト関数として機能します。 選択肢は true または false です。デフォルトは false です。 </td>
  </tr>
  <tr>
   <td colname="col1"> ワークスペースパス </td>
   <td colname="col2"> <p><i>オプション</i>. 特定のレポートセットのワークスペースのコレクションの場所。 複数のレポートセットに対して <span class="filepath"> Report.cfg </span> ファイルを使用して、複数の方法で生成および配布する必要があるワークスペースの 1 つのコピーを管理する場合に便利です。 このパスのルートディレクトリは、任意のプロファイルフォルダーにすることができます。 パス文字列の先頭にスラッシュ (\) を入力しないでください。 </p> <p>例：セット A とセット B の共通ワークスペースを <span class="filepath"> Reports\Common </span> フォルダーに保存し、2 つの異なるレポートセット用に <span class="filepath"> Report.cfg </span> ファイルを定義し、それぞれの生成と配布の設定を変えることができます。 両方の <span class="filepath"> Report.cfg </span> ファイルで、Workspace Path パラメーターを <i>profile name</i>\Reports\Commonに設定します。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> XSL 出力ファイル </td>
   <td colname="col2"> <i>オプション</i>. <span class="wintitle"> XSL テンプレート </span> がレポートインデックスに適用されたときに作成される出力ファイルのパス。 </td>
  </tr>
  <tr>
   <td colname="col1"> XSL テンプレート </td>
   <td colname="col2"> <p><i>オプション</i>. レポートインデックスに適用する XSL テンプレートファイルのパス。 変換後の <span class="filepath"> .xml </span> は、指定した <span class="wintitle"> XSL 出力ファイル </span> に書き込まれます。 サンプルファイルについては、「 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> レポートサンプルファイル </a> 」を参照してください。 </p> <p> <p>注意： レポートの生成時に <span class="filepath"> .xsl </span> テンプレートを使用しない限り、すべてのレポートは添付ファイルとして電子メールで配信されます。 </p> </p> </td>
  </tr>
 </tbody>
</table>
