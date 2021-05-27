---
description: Data WorkbenchのProfile Statusプロファイルでは、次のディメンションを使用できます。
title: Data Workbench プロファイルステータスプロファイルのディメンション
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench プロファイルステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-profile-status-profile}

Data WorkbenchのProfile Statusプロファイルでは、次のディメンションを使用できます。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> この設定で可算となるのはこれだけで、すべてのディメンションのルートとして存在します。 ブロックは、サーバーと見なすことができます。 x-trackingidフィールドを使用しています。 ブロックIDは、サーバー名とホスト名のハッシュなので、プロファイルごとにサーバーごとに約1ブロックあります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に丸められます。 As of Delay Minutesは、ブロックのLast Rowをx-as-of-delay-minutesから取る数値ディメンションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> cs-uri-query(c)値が環境IDに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境（正しく設定されている場合）を表示します。 <p>これは、 insight_monitor_agent.cfgファイルで設定できます </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>高速入力メガバイト/分</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputに含まれている場合、この数値Dimensionの値には、システムがデータを入力する1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1分あたりの高速マージメガバイト数</b> </td> 
   <td colname="col2">このディメンションにはcs-uri-query(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Merge This NumericDimensionの値には、システムがマージされる1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bg)値が使用されます。 値を1000で割り、最も近い整数に丸めます。 この数値Dimensionの値には、データセット内のフィールドで使用されている領域の量が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のping</b> </td> 
   <td colname="col2">x-last-pingは、x-unixtimeを10で除算します（数値ディメンションのサイズ制約に対応するため）。 最後のpingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時刻を表します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">cs-uri-query(be)値は、この数値ディメンションに使用されます。 これは、特定のブロックの最後の行です。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(bb)値が使用されます。 特定のブロックの最後の行です。 処理モードIDを使用すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは、クライアント側のディメンション処理モードで、わかりやすい値で再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> 「 x-processing-stalled 」フィールドは、プロファイルが現在実行中かどうかを示す様々な条件を使用して作成されます。 これは単純なディメンションです。 <p>注意： このディメンションは、多数の入力ログがDPU間で公平に分散されている場合に最も適しています。 例えば、1日に1つの大きなファイルのみが読み込まれた場合、Data Workbenchは、1時間以上「停止」するように表示され、このディメンションから偽陽性の読み取りがおこなわれます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(ba)値が使用されます。 このディメンションは、現在監視中のプロファイルの名前を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も後ろのソース</b> </td> 
   <td colname="col2"> cs-uri-query(bl)の最後の行がx-source-furthest-behindフィールドにコピーされます。 単純Dimensionは、特定のブロックに対して最後の行を使用します。 このディメンションは、データソースとの最後の連絡が発生した日時を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2"> cs-uri-query(bf)値は、この数値ディメンションに使用されます。 これは、特定のブロックの最後の行です。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間ディメンション</b> </td> 
   <td colname="col2"> Hour、Day、Week、Month、Hour of Day、Day of Weekはすべて、x-timestampフィールドから得られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供するグループ化語。 insight_monitor_agent.cfgファイルで設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次に、Data Workbenchのプロファイル監視プロファイルに含まれる指標と、それらの派生方法を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの基準遅延時間（分）の合計を、ブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（秒）</b> </td> 
   <td colname="col2"> このメトリックは、各ブロックの基準遅延秒の合計を、ブロックの合計数で割った値です。 (「遅延秒数」Dimensionが初期設定では設定されていない場合) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> 各ブロックに対して1つの合計。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MB/分</b> </td> 
   <td colname="col2"> Fast Input MegaBytes/Minuteが0より大きい場合、各ブロックのFast Input MegaBytes/Minuteの合計をブロック数で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MB/分</b> </td> 
   <td colname="col2"> Fast Merge MegaBytes/分が0より大きい場合、各ブロックのFast Merge MegaBytes/分の合計をブロック数で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> 各ブロックのフィールドGBの合計をブロック指標で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Age</b> </td> 
   <td colname="col2"> 現在時刻から最後のPing時間を引いた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>前回のping時間</b> </td> 
   <td colname="col2"> 各ブロックの最後のpingの合計をブロックで割って、10を掛けた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログの読み取り</b> </td> 
   <td colname="col2"> Log Reading Percentageが0より大きい場合、Log Readingは、各ブロックのLog Reading Percentageの合計です。Blocks指標で割り算され、すべて10で割られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Processing Stalled</b> </td> 
   <td colname="col2"> 各ブロックの処理停止Dimensionの合計をブロック指標で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換</b> </td> 
   <td colname="col2"> Transformation Percentageが0より大きい場合、各ブロックの変換の割合をBlocks指標で割った値の合計です。すべてを10で割ります。 </td> 
  </tr> 
 </tbody> 
</table>
