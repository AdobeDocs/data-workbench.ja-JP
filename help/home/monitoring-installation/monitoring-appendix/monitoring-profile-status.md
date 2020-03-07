---
description: 次のディメンションは、Data Workbenchのプロファイルステータスプロファイルで使用できます。
solution: Analytics
title: Data Workbenchのプロファイルステータスプロファイルのディメンション
topic: Data workbench
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchのプロファイルステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-profile-status-profile}

次のディメンションは、Data Workbenchのプロファイルステータスプロファイルで使用できます。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> この設定で可算となるのはこれだけで、すべてのディメンションのルートとして存在します。 ブロックはサーバーと見なすことができます。 x-trackingidフィールドを使用しています。 ブロックIDは、サーバ名とホスト名のハッシュです。したがって、プロファイルごとに1つのサーバに約1ブロックが存在します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に四捨五入されます。 At of Delay Minutesは、ブロックのLast Rowをx-as-of-delay-minutesから取る数値ディメンションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> cs-uri-query(c)値が環境IDに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルディメンションは、サーバーが正しく設定されている場合は、実行中の環境を表示します。 <p>これは、insight_monitor_agent.cfgファイルで設定できます </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MegaBytes/Minute</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputにある場合、この数値ディメンションの値には、システムがデータを入力する1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MegaBytes/Minute</b> </td> 
   <td colname="col2">このディメンションには、cs-uri-query(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Mergeに含まれる場合、この数値ディメンションの値には、システムがマージされる1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bg)値が使用されます。 値を1000で割り、最も近い整数に四捨五入します。 この数値ディメンションの値には、データセット内のフィールドで使用されている領域の量が表示されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2">x-last-pingは、（数値ディメンションのサイズ制約に対応するために）x-unixtimeを10で割る値です。 Last Pingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性をログに記録した時間を表します。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">この数値ディメンションには、cs-uri-query(be)値が使用されます。 特定のブロックの最後の行です。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> このシンプルディメンションには、cs-uri-query(bb)値が使用されます。 特定のブロックの最後の行です。 処理モードIDを使用すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは非表示になり、クライアント側のディメンションの処理モードでフレンドリ値を使用して再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>停止した処理</b> </td> 
   <td colname="col2"> 「x-processing-stalled」フィールドは、プロファイルが現在実行中かどうかを示す様々な条件を使用して作成されます。 これはシンプルな次元です。 <p>注意： このディメンションは、入力ログが大量に存在し、DPU間で均等に配布される場合に最も効果的です。 例えば、1日に1つの大きなファイルのみが読み込まれた場合、Data Workbenchは1時間以上「停止」したように表示され、このディメンションから偽の肯定的な読み取りが行われます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> このシンプルディメンションには、cs-uri-query(ba)値が使用されます。 このディメンションには、現在監視中のプロファイルの名前が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も背後のソース</b> </td> 
   <td colname="col2"> cs-uri-query(bl)の最後の行がx-source-furthest-behindフィールドにコピーされます。 シンプルディメンションは、特定のブロックの最後の行を使用します。 このディメンションには、データソースとの最後の接触が発生した日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2"> cs-uri-query(bf)値がこの数値ディメンションに使用されます。 特定のブロックの最後の行です。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間ディメンション</b> </td> 
   <td colname="col2"> 時間、日、週、月、時間帯、曜日はすべてx-timestampフィールドから派生します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供する単語をグループ化します。 insight_monitor_agent.cfgファイル内で設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> Data Workbenchのプロファイル監視プロファイルに含まれる指標と、その派生方法を以下に示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの「基準遅延時間（分）」の合計をブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>基準遅延秒数</b> </td> 
   <td colname="col2"> この指標は、各ブロックの基準遅延秒数の合計を、ブロックの合計数で割った値です。 （遅延秒数ディメンションが設定されていない場合） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> 各ブロックに対して1つの合計を求めます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MB/分</b> </td> 
   <td colname="col2"> Fast Input MegaBytes/Minuteが0より大きい場合の、各ブロックのFast Input MegaBytes/Minuteの合計をブロック数で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MB/分</b> </td> 
   <td colname="col2"> Fast Merge MegaBytes/Minuteの合計が0より大きい場合、各ブロックの1分あたりのFast Merge MegaBytesの数をブロック数で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> 各ブロックのフィールドギガバイトの合計をブロック指標で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPingの時間</b> </td> 
   <td colname="col2"> 基準時間から前回のPing時間を引いた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Time</b> </td> 
   <td colname="col2"> 各ブロックの最後のpingの合計をブロックで割って、10を掛けた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログの読み取り</b> </td> 
   <td colname="col2"> Log Reading Percentageが0より大きい場合、Log Readingは各ブロックのLog Reading Percentageの合計をBlocks指標で割った値で、すべて10で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>停止した処理</b> </td> 
   <td colname="col2"> 各ブロックの処理停止ディメンションの合計を、ブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換</b> </td> 
   <td colname="col2"> 各ブロックの変換の割合をブロック指標で割った値の合計です。変換の割合が0より大きい場合は、すべて10で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>

