---
description: 次のディメンションは、Data Workbench の Profile Status プロファイルで使用できます。
title: Data Workbench プロファイルステータスプロファイルのディメンション
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench プロファイルステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-profile-status-profile}

{{eol}}

次のディメンションは、Data Workbench の Profile Status プロファイルで使用できます。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> この設定で可算となるのはこれだけで、すべてのディメンションのルートとして存在します。 ブロックは、サーバーと見なすことができます。 x-trackingid フィールドを使用しています。 ブロック ID は、サーバー名とホスト名のハッシュなので、プロファイルごとにサーバーごとに約 1 ブロック存在します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi) は、x-as-of-delay-minutes フィールドに配置され、最も近い分に丸められます。 As of Delay Minutes は、ブロックの最終行を x-as-of-delay-minutes から取得する数値ディメンションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> cs-uri-query(c) 値は環境 ID に使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境を表示します（適切に設定されている場合）。 <p>これは、 insight_monitor_agent.cfg ファイルで設定できます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>高速入力メガバイト/分</b> </td> 
   <td colname="col2"> cs-uri-query(bj) 値がこのディメンションに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットが高速入力の場合、この数値Dimensionの値には、システムがデータを入力する時点の MB/分が表示されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1 分あたりの高速マージメガバイト数</b> </td> 
   <td colname="col2">cs-uri-query(bk) 値がこのディメンションに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットが高速結合の場合、この数値Dimensionの値には、システムが結合する時点の MB/分が表示されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>フィールド GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bg) 値がこのディメンションに使用されます。 値を 1000 で割り、最も近い整数に丸めます。 この数値Dimensionの値には、データセット内のフィールドが使用している容量が表示されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> cs-uri-query(b) 値がこのディメンションに使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後の Ping</b> </td> 
   <td colname="col2">x-last-ping は、x-unixtime を 10 で割る値です（数値ディメンションのサイズ制約に対応するため）。 「最後の ping 」は、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時点を表します。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">cs-uri-query(be) 値は、この数値ディメンションに使用されます。 特定のブロックの最後の行です。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モード ID</b> </td> 
   <td colname="col2"> このシンプルDimensionには、cs-uri-query(bb) 値が使用されます。 特定のブロックの最後の行です。 処理モード ID を使用すると、システムの処理モード（高速入力、高速結合、リアルタイム）を確認できます。 <p>注意：このディメンションは、非表示になり、クライアント側のディメンションの処理モードでわかりやすい値で再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> 「 x-processing-stalled 」フィールドは、プロファイルが現在実行中かどうかを示すための様々な条件を使用して作成されます。 これは単純なディメンションです。 <p>注意：このディメンションは、多数の入力ログが DPU 間で公平に分散されている場合に最も適しています。 例えば、1 日に 1 つの大きなファイルのみが読み込まれた場合、Data Workbench は 1 時間以上「停止」するように表示され、このディメンションから偽陽性の読み取りがおこなわれます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> このシンプルDimensionには cs-uri-query(ba) 値が使用されます。 このディメンションは、現在監視中のプロファイルの名前を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も遠い後のソース</b> </td> 
   <td colname="col2"> cs-uri-query(bl) の最後の行が x-source-furthest-behind フィールドにコピーされます。 簡易Dimensionは、特定のブロックの最後の行を使用します。 このディメンションは、データソースとの最後の連絡が発生した日時を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2"> cs-uri-query(bf) 値は、この数値ディメンションに使用されます。 特定のブロックの最後の行です。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間ディメンション</b> </td> 
   <td colname="col2"> 「時間」、「日」、「週」、「月」、「時間帯」および「曜日」は、すべて x-timestamp フィールドから派生します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供する単語をグループ化します。 insight_monitor_agent.cfg ファイルで設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次に、Data Workbench のプロファイル監視プロファイルに含まれる指標と、その派生方法を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの遅延時間（分）の合計をブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（秒）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの遅延時間（秒）の合計値をブロックの総数で割った値です。 (「遅延秒数」Dimensionが初期設定では設定されていません ) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> ブロックごとに 1 つの合計を求めます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1 分あたりの高速入力 MB</b> </td> 
   <td colname="col2"> Fast Input MegaBytes/分が 0 より大きい場合、各ブロックの Fast Input MegaBytes/分の合計をブロック数で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1 分あたりの高速結合 MB</b> </td> 
   <td colname="col2"> Fast Merge MegaBytes/分が 0 より大きい場合、各ブロックの Fast Merge MegaBytes/分の合計をブロック数で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>フィールド GigaBytes</b> </td> 
   <td colname="col2"> 各ブロックのフィールド GB の合計をブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>前回の Ping の経過時間</b> </td> 
   <td colname="col2"> 現在時刻から最後の Ping 時間を引いた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>前回の Ping 時間</b> </td> 
   <td colname="col2"> 各ブロックの最後の ping の合計をブロックで割って、10 を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログの読み取り</b> </td> 
   <td colname="col2"> Log Reading Percentage が 0 より大きい場合、Log Reading は、各ブロックのログ読み取りの割合の合計です。Blocks 指標で割られ、すべて 10 で割られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> 各ブロックの処理停止Dimensionの合計（Blocks 指標で割る）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換</b> </td> 
   <td colname="col2"> 各ブロックの変換の割合の合計を Blocks 指標で割った値です。Transformation Percentage が 0 より大きい場合は、すべて 10 で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>
