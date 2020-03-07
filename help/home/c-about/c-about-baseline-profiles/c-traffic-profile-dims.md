---
description: トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ次元が含まれています。
solution: Analytics
title: トラフィックプロファイルディメンション
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# トラフィックプロファイルディメンション{#traffic-profile-dimensions}

トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ次元が含まれています。

次の表に示すディメンションは、Traffic\Dataset\Transformation directoryフォルダーの変換データセットインクルードファイルで定義されています。

| 名前 | タイプ | レベル | 説明 |
|---|---|---|---|
| 日 | シンプル | セッション | セッションの最初のログエントリの日。 |
| 曜日 | シンプル | セッション | セッションの最初のログエントリの曜日。 |
| 正確なページ期間（非表示） | 数値 | ページビュー | ページビューの時間から次のページビューの時間を引いて測定した、ページビューの時間（ミリ秒）。 セッションの最後のページビューの正確な時間は、常に0です。 |
| 時間 | シンプル | セッション | セッションの最初のログエントリの時間。 |
| 時刻 | シンプル | セッション | セッションの最初のログエントリの時刻。 |
| 月 | シンプル | セッション | セッションの最初のログエントリの月。 |
| ページビュー | 可算 | セッション | Page View Conditionを満たすログエントリまたは「イベントデータレコード」。 |
| リファラー | シンプル | セッション | セッションの最初のログエントリのリファラーの第2レベルのドメイン（内部リファラードメインの場合は「なし」）。 |
| セッション | 可算 | 訪問者 | 訪問者による、関連する連続したアクティビティの期間。 30分間の無操作状態と外部リファラードメイン、または48時間の最大セッション時間で区切られます。 これらのタイムアウトと、内部ドメインと見なされる一連のドメインの両方をファイル内で設定で [!DNL Transformation.cfg] きます。 |
| URI | シンプル | ページビュー | ページビューのURIステム。 URIディメンションは、ReplaceURI、PrependURIおよびAppendURI変換を使用して再定義できます。 |
| 訪問者 | 可算 | 該当なし | x-trackingidの一意の値。 永続的なcookieが使用される場合、通常は一意のブラウザーに対応します。 それ以外の場合は、x-trackingidは、IP番号やx.509の共通名など、他の一意の識別子に基づくことができます。 |
| 週 | シンプル | セッション | セッションの最初のログエントリの週。 |

次の表に示すディメンションは、トラフィックプロファイルのDimensionディレクトリで定義されています。

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ディメンション </th> 
   <th colname="col2" class="entry"> タイプ </th> 
   <th colname="col03" class="entry"> レベル </th> 
   <th colname="col3" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ブラウザー </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> 訪問者 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ（バージョン番号を含む）（MSIE 6.0など）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ブラウザーのタイプ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> 訪問者 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ（MSIEなど）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付き検索エンジンから検索した場合の、訪問者のセッションの最初の検索エンジン。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 次のURI </td> 
   <td colname="col2"> 派生（URIディメンションに基づくShiftDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 現在選択されているURIの後の次のURIのURI。 この派生ディメンションは、任意のURIの後で訪問者が次に何を行うかに関する分析を行うために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1回限りと繰り返し </td> 
   <td colname="col2"> 派生（リピート訪問者数指標と1回限りの訪問者数指標に基づくSegmentDim） </td> 
   <td colname="col03"> 訪問者 </td> 
   <td colname="col3"> 訪問者のタイプ：1回のみまたは繰り返し。 1回限りの訪問者はサイトで1回のセッションしか持っていないのに対し、再訪問者は複数のセッションを持っています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ </td> 
   <td colname="col2"> 派生（URIディメンションに基づくRenameDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> セッション中に訪問された各ページの名前。 最初は、各ページの名前はURIと同じですが、解釈しやすくするために変更できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リファラー </td> 
   <td colname="col2"> 組み込みリファラーディメンションから継承 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者のブラウザーが提供する、サイトへの最初のセッションを参照したWebサイトの第2レベルのドメイン名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索フレーズ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が指定の検索エンジンから検索を行ったときに、その訪問者のセッションで検索エンジンによって渡される最初の検索フレーズ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索語句 </td> 
   <td colname="col2"> 多対多 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者が指定の検索エンジンから検索リファラークリックスルーを受け取った場合に、検索エンジンによって渡される各検索用語。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション時間 </td> 
   <td colname="col2"> 派生（正確なページ期間指標に基づくMetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 30秒単位のセッションの時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション番号 </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者がサイトを訪問した回数。 例えば、初回訪問者のセッション番号は「1」、2回目訪問者のセッション番号は「2」などです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づくMetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション内のページビュー数。 例えば、Session Page Viewsディメンションで「3」を選択すると、正確に3ページビューのすべてのセッションが選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション中に訪問者をサイトに導いた名前付き検索エンジンである最初のWebサイトの第2レベルのドメイン名（訪問者のブラウザーの提供による）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間ディメンション </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションが開始された時間、日、時間、週、曜日、月、四半期、年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間レポートディメンション </td> 
   <td colname="col2"> 派生（組み込み時間ディメンションに基づくLastNディメンションおよび名前の変更） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> ディメンションには、前日、先月の日、先週の日、今月の日、今日の時間、昨日の時間、過去12か月、過去2週間、過去24時間、過去3か月、過去4週間、過去6か月が含まれます。7日間、過去7日間と今日、過去8週間、過去9週間、過去9か月、先週、前月、今月、今月、過去14日間、このおよび過去6か月、このおよび過去8週間、今日、今日および過去30日「前」と「昨日」は、常にデータセットの一部のデータを表示するワークスペースまたはレポートを作成する便利な方法を提供します。 それぞれ、セッションが開始された時期に基づきます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 組み込みディメンションURIから継承 </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 表示された各ページのURI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者ページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づくMetricDim） </td> 
   <td colname="col03"> 訪問者 </td> 
   <td colname="col3"> 1人の訪問者に対する現在までのページビュー数。 例えば、Visitor Page Viewsディメンションで「3」を選択すると、すべてのセッションで正確に3ページビューの訪問者がすべて選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者リファラー </td> 
   <td colname="col2"> 組み込みディメンションリファラーから継承 </td> 
   <td colname="col03"> 訪問者 </td> 
   <td colname="col3"> 訪問者が最初のセッション（訪問者のブラウザーの指定に従う）でサイトに最初に訪問したWebサイトの第2レベルのドメイン名。 </td> 
  </tr> 
 </tbody> 
</table>

