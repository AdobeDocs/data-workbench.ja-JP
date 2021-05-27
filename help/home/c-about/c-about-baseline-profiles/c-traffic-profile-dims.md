---
description: トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ、次のディメンションが含まれています。
title: トラフィックプロファイルのディメンション
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 10%

---

# トラフィックプロファイルのディメンション{#traffic-profile-dimensions}

トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ、次のディメンションが含まれています。

次の表に示すディメンションは、 Traffic\Dataset\Transformation directoryフォルダー内の変換データセットインクルードファイルで定義されています。

| 名前 | タイプ | レベル | 説明 |
|---|---|---|---|
| 日 | シンプル | セッション | セッションの最初のログエントリの日。 |
| 曜日 | シンプル | セッション | セッションの最初のログエントリの曜日。 |
| 正確なページ期間（非表示） | 数値 | ページビュー | ページビューの時間から次のページビューの時間を引くことで測定される、ページビューの時間（ミリ秒）。 セッションの最後のページビューの正確な時間は常に0です。 |
| 時間 | シンプル | セッション | セッションの最初のログエントリの時間。 |
| 時刻 | シンプル | セッション | セッションの最初のログエントリの時刻。 |
| 月 | シンプル | セッション | セッションの最初のログエントリの月。 |
| ページビュー | 可算 | セッション | Page View Conditionを満たすログエントリまたは「Event Data Record」。 |
| リファラー | シンプル | セッション | セッションの最初のログエントリのリファラーの第2レベルドメイン（内部リファラードメインの場合は「なし」）。 |
| セッション | 可算 | 訪問者。 | 訪問者による関連する連続アクティビティの期間。 無操作状態が30分間続く外部リファラードメインまたは最大48時間のセッション期間で区切られます。 これらのタイムアウトと、内部と見なされる一連のドメインは、どちらも[!DNL Transformation.cfg]ファイルに設定できます。 |
| URI | シンプル | ページビュー | ページビューのURIステム。 このURIディメンションは、 ReplaceURI 、 PrependURI 、 AppendURIの各変換を使用して再定義できます。 |
| 訪問者。 | 可算 | 該当なし | x-trackingidの一意の値。 永続的なcookieを使用する場合、通常は一意のブラウザーに対応します。 x-trackingidは、IP番号やx.509共通名などの一意の識別子に基づくものです。 |
| 週 | シンプル | セッション | セッションの最初のログエントリの週。 |

次の表に示すディメンションは、トラフィックプロファイルのDimensionディレクトリで定義されます。

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
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ(バージョン番号（MSIE 6.0など） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ブラウザータイプ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ（例：MSIE）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付きの検索エンジンから検索したときの、訪問者のセッションの最初の検索エンジン。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 次のURI </td> 
   <td colname="col2"> 派生（URIディメンションに基づくShiftDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 現在選択されているURIの後の次のURIのURI。 この派生ディメンションは、特定のURIの後に訪問者が何を行うかに関する分析を行うために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1回のみ </td> 
   <td colname="col2"> 派生（リピート訪問者数指標と1回限りの訪問者数指標に基づくSegmentDim） </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者のタイプ：1回または繰り返し。 1回限りの訪問者はサイトで1回のセッションしか行っていないのに対し、リピート訪問者は複数のセッションを行っている。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ </td> 
   <td colname="col2"> 派生（URIディメンションに基づくRenameDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> セッション中に訪問された各ページの名前。 最初は、各ページの名前はURIと同じですが、解釈を容易にするために変更できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リファラー </td> 
   <td colname="col2"> 組み込みのリファラーディメンションから継承 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者のブラウザーから提供される、最初にサイトにセッションを参照したWebサイトの第2レベルのドメイン名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索語句 </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付きの検索エンジンから検索を行ったときに、訪問者のセッションの最初の検索フレーズが検索エンジンによって渡される。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索語句 </td> 
   <td colname="col2"> 多対多 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者が名前付き検索エンジンから検索リファラークリックスルーを持つ場合に検索エンジンによって渡される各検索語句。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション時間 </td> 
   <td colname="col2"> 派生（正確なページ期間指標に基づくMetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションの時間（30秒単位）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション番号 </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者がサイトを訪問した回数。 例えば、初回訪問者のセッション番号は「1」、2回目訪問者のセッション番号は「2」といった具合です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションのページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づくMetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション内のページビュー数。 例えば、Session Page Viewsディメンションで「3」を選択すると、ページビューが3つのすべてのセッションが選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者がセッション中にサイトに来訪した（訪問者のブラウザーから提供された）名前付き検索エンジンである最初のWebサイトの第2レベルのドメイン名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間ディメンション </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションが開始された時間、日、時間、週、曜日、月、四半期、年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間レポートのDimension </td> 
   <td colname="col2"> 派生（組み込みの時間ディメンションに基づくLastNおよび名前変更ディメンション） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> Dimension(前日、前月の日、先週の日、今月の日、今日の日、今日の時間、昨日の時間、過去12ヶ月、過去2週間、過去24時間、過去3ヶ月、過去4週間、過去6ヶ月、7日間、過去7日間、今日、過去8週間、過去9ヶ月、過去9ヶ月、過去9ヶ月、先月、先週、今月、今週、過去14日、今週、過去6ヶ月、今日、今日、今日、今日、過去8週間、今日、過去30日、「Ago」と「Yesterday」は、データセット内のデータの一部を常に表示するワークスペースまたはレポートを作成する便利な方法を提供します。 それぞれは、セッションが開始されたタイミングに基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 組み込みのDimensionURIから継承 </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 表示された各ページのURI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者のページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づくMetricDim） </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者に対する現在のページビュー数。 例えば、訪問者ページビュー数ディメンションで「3」を選択すると、すべてのセッションで、ページビュー数が3回の訪問者がすべて選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者リファラー </td> 
   <td colname="col2"> 組み込みディメンションリファラーから継承 </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 最初のセッションで訪問者をサイトに導いたWebサイトの第2レベルのドメイン名（訪問者のブラウザーから提供される名前）。 </td> 
  </tr> 
 </tbody> 
</table>
