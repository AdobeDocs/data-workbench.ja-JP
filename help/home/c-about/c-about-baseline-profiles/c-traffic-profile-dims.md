---
description: トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ次のディメンションが含まれています。
title: トラフィックプロファイルのディメンション
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 10%

---

# トラフィックプロファイルのディメンション{#traffic-profile-dimensions}

トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ次のディメンションが含まれています。

次の表に示すディメンションは、Traffic\Dataset\Transformation directoryフォルダーの変換データセットインクルードファイルで定義されています。

| 名前 | タイプ | レベル | 説明 |
|---|---|---|---|
| 日 | シンプル | セッション | セッションの最初のログエントリの日。 |
| 曜日 | シンプル | セッション | セッションの最初のログエントリの曜日。 |
| 正確なページ期間（非表示） | 数値 | ページビュー | ページ表示の時間から次のページ表示の時間を引いて測定したページ表示時間（ミリ秒）。 セッションの最後のページ表示の正確な時間は、常に0です。 |
| 時間 | シンプル | セッション | セッションの最初のログエントリの時間。 |
| 時刻 | シンプル | セッション | セッションの最初のログエントリの時刻。 |
| 月 | シンプル | セッション | セッションの最初のログエントリの月。 |
| ページビュー | 可算 | セッション | Page Data Conditionを満たすログエントリ、または「イベント表示レコード」。 |
| リファラー | シンプル | セッション | セッションの最初のログエントリの転送者の2番目のレベルドメイン(内部転送者ドメインの場合はNone)。 |
| セッション | 可算 | 訪問者。 | 訪問者による関連する連続アクティビティの期間。 セッション期間は、30分間の無操作状態と外部転送者ドメイン、または48時間の最大セッション期間で区切られます。 これらのタイムアウトと、内部ドメインと見なされる一連のドメインは、どちらも[!DNL Transformation.cfg]ファイル内に設定できます。 |
| URI | シンプル | ページビュー | ページ表示のURIステム。 URIディメンションは、ReplaceURI、PrependURI、AppendURIの各変換を使用して再定義できます。 |
| 訪問者。 | 可算 | 該当なし | x-trackingidの一意の値。 持続的cookieを使用する場合、通常は一意のブラウザーに対応します。 x-trackingidは、IP番号やx.509共通名などの一意の識別子に基づく場合もあります。 |
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
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ。バージョン番号（MSIE 6.0など）が含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ブラウザータイプ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ（MSIEなど）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付きの検索エンジンから検索を行った場合に、その訪問者のセッションで最初に行われた検索エンジン。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 次のURI </td> 
   <td colname="col2"> 派生（URIディメンションに基づくShiftDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 現在選択されているURIの後の次のURI。 この派生ディメンションは、任意のURIの後で訪問者が次に何を行うかに関する分析を行うために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1回のみと繰り返し </td> 
   <td colname="col2"> 派生(繰り返し訪問者と1回限りの訪問者指標に基づくSegmentDim) </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者のタイプ：1回のみまたは繰り返し。 1回限りの訪問者はサイト上で1つのセッションしか持っていませんが、リピート訪問者は複数のセッションを持っています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ </td> 
   <td colname="col2"> 派生（URIディメンションに基づくRenameDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> セッション中に訪問された各ページの名前。 最初は、各ページの名前はURIと同じですが、解釈しやすくするために変更できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リファラー </td> 
   <td colname="col2"> 組み込み転送者ディメンションから継承 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 最初に訪問者をサイトに導いたWebサイトの第2レベルのドメイン名（ブラウザの指定に従います）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索フレーズ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付き検索エンジンから検索を行ったときに、その訪問者のセッションで最初に渡される検索フレーズです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索語句 </td> 
   <td colname="col2"> 多対多 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者が名前付き検索エンジンから検索転送者クリックスルーを取得した場合に、検索エンジンによって渡される各検索用語。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション期間 </td> 
   <td colname="col2"> 派生（正確なページ期間指標に基づくMetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 30秒単位のセッションの時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション番号 </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者がサイトを訪問した回数。 例えば、初回訪問者のセッション番号は「1」、2回目の訪問者のセッション番号は「2」、などです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションページの表示 </td> 
   <td colname="col2"> 派生(ページ表示指標に基づくMetricDim) </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション内のページ表示数。 例えば、Session Page Sessionsディメンションで「3」を選択すると、正確に3つのページ表示を持つすべての表示が選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション中に訪問者をサイトに導いた(訪問者のブラウザーの指定に従って)、名前付き検索エンジンである最初のWebサイトの第2レベルのドメイン名です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間ディメンション </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションが開始した時間、日、時間、週、曜日、月、四半期、年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> レポートDimension </td> 
   <td colname="col2"> 派生（組み込みの時間ディメンションに基づくLastNディメンションおよび名前の変更） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 前日、先月の日数、先週の日数、今月の日数、今週の日数、今日の時間、昨日の時間、過去12か月、過去2か月、過去24時間、過去3か月、過去4週間、過去6か月を含むDimension7日間、過去7日間と今日、過去8週間、過去9週間、過去9か月、先月、先月、今月、今週、今週、過去14日間、過去6か月、今日、今日、今日、レポート、過去30日、AgoとYesterdayは、常にデータセット内の一部のデータを示すワークスペースまたはレポートを作成する便利な方法を提供します。 それぞれは、セッションの開始時期に基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 組み込みDimensionURIから継承 </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 表示された各ページのURI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者ページの表示 </td> 
   <td colname="col2"> 派生(ページ表示指標に基づくMetricDim) </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者の現在までのページ表示数。 例えば、訪問者ページの表示ディメンションで「3」を選択すると、すべてのセッションで、正確に3つのページ表示を持つすべての訪問者が選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者リファラー </td> 
   <td colname="col2"> 組み込みディメンション転送者から継承 </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 最初のセッションで訪問者をサイトに導いた最初のWebサイトの第2レベルのドメイン名(訪問者のブラウザーの指定に従います)。 </td> 
  </tr> 
 </tbody> 
</table>
