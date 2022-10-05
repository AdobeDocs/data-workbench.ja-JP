---
description: トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ、次のディメンションが含まれています。
title: トラフィックプロファイルのディメンション
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 10%

---

# トラフィックプロファイルのディメンション{#traffic-profile-dimensions}

{{eol}}

トラフィックプロファイルには、訪問者のアクションを識別するのに役立つ、次のディメンションが含まれています。

次の表に示すディメンションは、 Traffic\Dataset\Transformation ディレクトリ内の変換データセットインクルードファイルに定義されています。

| 名前 | タイプ | レベル | 説明 |
|---|---|---|---|
| 日 | シンプル | セッション | セッションの最初のログエントリの日。 |
| 曜日 | シンプル | セッション | セッションの最初のログエントリの曜日。 |
| 正確なページ期間（非表示） | 数値 | ページビュー | ページビューの時間から次のページビューの時間を引くことで測定される、ページビューの時間（ミリ秒単位）。 セッションの最後のページ表示時間の正確な長さは常に 0 です。 |
| 時間 | シンプル | セッション | セッションの最初のログエントリの時間。 |
| 時刻 | シンプル | セッション | セッションの最初のログエントリの時刻。 |
| 月 | シンプル | セッション | セッションの最初のログエントリの月。 |
| ページビュー | 可算 | セッション | Page View Condition を満たすログエントリまたは「Event Data Record」。 |
| リファラー | シンプル | セッション | セッションの最初のログエントリのリファラーの第 2 レベルドメイン（内部リファラードメインの場合は「なし」）。 |
| セッション | 可算 | 訪問者。 | 訪問者による関連する連続したアクティビティの期間。 無操作状態が 30 分間続くと外部リファラードメインまたは最大 48 時間のセッション期間で区切られます。 これらのタイムアウトと、内部と見なされる一連のドメインは、どちらも [!DNL Transformation.cfg] ファイル。 |
| URI | シンプル | ページビュー | ページビューの URI ステム。 URI ディメンションは、 ReplaceURI 、 PrependURI 、 AppendURI の各変換を使用して再定義できます。 |
| 訪問者。 | 可算 | 該当なし | x-trackingid の一意の値。 永続的な cookie を使用する場合、通常は一意のブラウザーに対応します。 x-trackingid は、IP 番号や、x.509 共通名などの一意の識別子に基づくものにすることができます。 |
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
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ。バージョン番号（MSIE 6.0 など）も含まれます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ブラウザータイプ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者が使用するユーザーエージェントのタイプ（MSIE など）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が特定の検索エンジンから検索したときの、訪問者のセッションで最初の検索エンジン。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 次の URI </td> 
   <td colname="col2"> 派生（URI ディメンションに基づく ShiftDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 現在選択されている URI の後の次の URI の URI。 この派生ディメンションは、特定の URI の後で訪問者が次に何をするかに関する分析を実行するために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 回限りと繰り返し </td> 
   <td colname="col2"> 派生（リピート訪問者および 1 回限りの訪問者指標に基づく SegmentDim） </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者のタイプ：1 回または繰り返し。 1 回限りの訪問者はサイトで 1 回のセッションしか行っていませんが、リピート訪問者は複数のセッションを行っています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ページ </td> 
   <td colname="col2"> 派生（URI ディメンションに基づく RenameDim） </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> セッション中に訪問された各ページの名前。 最初は、各ページの名前は URI と同じですが、解釈しやすくするために変更できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> リファラー </td> 
   <td colname="col2"> 組み込みのリファラーディメンションから継承 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者のブラウザーから提供される、サイトへのセッションを最初に参照した Web サイトの第 2 レベルのドメイン名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索フレーズ </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03">セッション <p>最初の行 </p></td> 
   <td colname="col3"> 訪問者が名前付きの検索エンジンから検索したときに検索エンジンによって渡される、訪問者のセッションの最初の検索フレーズ。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索語 </td> 
   <td colname="col2"> 多対多 </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者が名前付きの検索エンジンからの検索リファラークリックスルーを持つ場合に、検索エンジンによって渡される各検索語句。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション時間 </td> 
   <td colname="col2"> 派生（ExactPage Duration 指標に基づく MetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションの持続時間（30 秒単位）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッション番号 </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> 訪問者がサイトを訪問した回数。 例えば、初回訪問者のセッション番号は「1」、2 回目訪問者のセッション番号は「2」です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> セッションのページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づく MetricDim） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションでのページビュー数。 例えば、「セッションページビュー」ディメンションで「3」を選択すると、ページビューが 3 つだけのすべてのセッションが選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 検索エンジン </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッション中に訪問者をサイトに導いた名前付きの検索エンジンである最初の Web サイトの第 2 レベルのドメイン名（訪問者のブラウザーから提供されるもの）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間ディメンション </td> 
   <td colname="col2"> シンプル </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> セッションが開始した時間、日、時間、週、曜日、月、四半期、年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間レポートDimension </td> 
   <td colname="col2"> 派生（組み込みの時間ディメンションに基づく LastN および名前の変更ディメンション） </td> 
   <td colname="col03"> セッション </td> 
   <td colname="col3"> Dimension（前日、先月の日、先週の日、今月の日、今日の日、今日の時間、昨日の時間、過去 12 ヶ月、過去 2 週間、過去 24 時間、過去 3 ヶ月、過去 4 週間、過去 6 ヶ月、）7 日、過去 7 日間、過去 8 週間、過去 9 ヶ月、過去 9 ヶ月、過去 9 ヶ月、過去 1 週間、今週、今週、過去 14 日間、今月、過去 6 ヶ月、今日、今日、今日、今日、今日、過去 30 日間、前日と前日は、データセット内のデータの一部を常に表示するワークスペースまたはレポートを作成する便利な方法です。 それぞれ、セッションが開始されたタイミングに基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 組み込みDimensionURI から継承 </td> 
   <td colname="col03"> ページビュー </td> 
   <td colname="col3"> 表示された各ページの URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者のページビュー数 </td> 
   <td colname="col2"> 派生（ページビュー数指標に基づく MetricDim） </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 訪問者に対する今までのページビュー数。 例えば、訪問者ページビュー数ディメンションで「3」を選択すると、すべてのセッションで、ページビューが 3 つだけの訪問者が選択されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問者リファラー </td> 
   <td colname="col2"> 組み込みディメンションリファラーから継承 </td> 
   <td colname="col03"> 訪問者。 </td> 
   <td colname="col3"> 最初のセッションで訪問者をサイトに導いた Web サイトの第 2 レベルのドメイン名（訪問者のブラウザーから提供される名前）。 </td> 
  </tr> 
 </tbody> 
</table>
