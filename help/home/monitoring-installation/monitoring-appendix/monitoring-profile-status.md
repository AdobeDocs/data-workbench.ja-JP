---
description: 次のディメンションは、Data Workbenchプロファイルのステータスプロファイルで使用できます。
title: Data Workbench プロファイルステータスプロファイルのディメンション
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench プロファイルステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-profile-status-profile}

次のディメンションは、Data Workbenchプロファイルのステータスプロファイルで使用できます。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> これはこの設定での唯一の可算であり、すべてのディメンションのルートとして存在します。 ブロックはサーバーと見なすことができます。 x-trackingidフィールドを使用しています。 ブロックIDは、サーバ名とホスト名のハッシュです。したがって、プロファイルごとに約1ブロックあります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）の基準</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に丸められます。 At of Delay Minutesは、ブロックのLast Rowをx-as-of-delay-minutesから取る数値ディメンションです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> 環境IDにはcs-uri-クエリ(c)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境を表示します（正しく設定されている場合）。 <p>これは、insight_monitor_agent.cfgファイルで設定できます </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MegaBytes/Minute</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputに含まれている場合、この数値Dimensionの値には、システムがデータを入力する1分あたりのMBが表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MegaBytes/Minute</b> </td> 
   <td colname="col2">この寸法には、cs-uri-クエリ(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Mergeに設定されている場合、この数値Dimensionの値には、システムがマージされる1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(bg)値が使用されます。 値を1000で割り、最も近い整数に丸めます。 この数値Dimensionの値は、データセット内のフィールドで使用されている領域のサイズを表示します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2">x-last-pingは、x-unixtimeを10で割る（数値ディメンションのサイズ制約に対応する）ことです。 Last Pingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時刻を表します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Log Reading Percentage</b> </td> 
   <td colname="col2">この数値ディメンションには、cs-uri-クエリ(be)値が使用されます。 特定のブロックの最後の行です。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> この単純なDimensionには、cs-uri-クエリ(bb)値が使用されます。 特定のブロックの最後の行です。 処理モードIDを使用すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは、非表示になった後、クライアント側のディメンション処理モードでフレンドリ値を使用して再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>停止した処理</b> </td> 
   <td colname="col2"> 「x-processing-stalled」フィールドは、プロファイルが現在実行中かどうかを示す様々な条件で作成されます。 これは単純な次元です。 <p>注意： このディメンションは、入力ログが大量に存在し、DPU間で公平に配布されている場合に最も適しています。 例えば、1日に1つの大きなファイルのみが読み込まれた場合、data workbenchは1時間以上「停止」した状態で表示され、このディメンションから偽の正値の読み取りが行われます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> この単純なDimensionには、cs-uri-クエリ(ba)値が使用されます。 このディメンションには、現在監視中のプロファイルの名前が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も後のソース</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bl)の最後の行がx-source-furthest-behindフィールドにコピーされます。 単純Dimensionでは、特定のブロックの最後の行を使用します。 このディメンションには、データソースとの最後の接触が発生した日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2"> この数値ディメンションには、cs-uri-クエリ(bf)値が使用されます。 特定のブロックの最後の行です。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間ディメンション</b> </td> 
   <td colname="col2"> 時間、日、週、月、時間帯、曜日はすべて、x-timestampフィールドから派生します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供するグループ化語。 insight_monitor_agent.cfgファイル内に設定します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次のリストには、data workbenchプロファイルの監視プロファイルに含まれる指標とその派生方法が示されています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの基準遅延時間（分）の合計をブロック指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>基準遅延時間（秒）</b> </td> 
   <td colname="col2"> この指標は、各ブロックの基準遅延秒の合計をブロックの合計数で割った値です。 (遅延時間（秒）のDimensionが初期設定で設定されていません) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2"> 各ブロックに1つ合計します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MB/分</b> </td> 
   <td colname="col2"> 各ブロックのFast Input MegaBytes/Minuteの合計を、Fast Input MegaBytes/Minuteが0より大きい場合のブロック数で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MB/分</b> </td> 
   <td colname="col2"> Fast Merge MegaBytes/Minuteが0より大きい場合、各ブロックのFast Merge MegaBytes/Minuteの合計をブロック数で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2"> 各ブロックのフィールドギガバイトの合計をブロック数指標で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Age</b> </td> 
   <td colname="col2"> 基準時点から最後のPing時間を引いた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最終Ping時間</b> </td> 
   <td colname="col2"> 各ブロックの最後のpingの合計をブロックで割って、10を掛けた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログの読み取り</b> </td> 
   <td colname="col2"> Log Reading Percentageが0より大きい場合、Log Readingは、各ブロックのログ読み取りの割合の合計をブロック指標で割った値です。すべて10で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>停止した処理</b> </td> 
   <td colname="col2"> 各ブロックの処理停止Dimensionの合計をブロック指標で割った値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換</b> </td> 
   <td colname="col2"> 各ブロックの変換率の合計をブロック数指標で割った値です。変換率が0より大きい場合、すべて10で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>
