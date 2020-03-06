---
description: 次のディメンションは、Data Workbenchサーバーのステータスプロファイルで使用できます。
solution: Analytics
title: Data Workbenchサーバーのステータスプロファイルのディメンション
topic: Data workbench
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchサーバーのステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-server-status-profile}

次のディメンションは、Data Workbenchサーバーのステータスプロファイルで使用できます。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> この可算ディメンションは、x-trackingidフィールドから構築され、Data Workbenchを実行しているサーバーを表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エージェントバージョン</b> </td> 
   <td colname="col2"> このシンプルディメンションには、cs-uri-query(af)値が使用されます。 サーバーの最後の空白以外の値です。 実行中の監視エージェントのバージョンのビルド日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任意のプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)フィールドは、この数値ディメンションに使用されます。これは、特定のサーバーの最後の行の値で、cs-uri-query(k)に条件が当てはまります。 このディメンションは、再処理中のプロファイルがあるかどうかを示すために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>生産能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r)フィールドは、この数値ディメンションに使用されます。これは、特定のサーバーの最後の行の値で、cs-uri-query(k)に条件が当てはまります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n)フィールドは、この数値ディメンションに使用されます。これは、特定のサーバーの最後の行の値で、cs-uri-query(k)に条件が当てはまります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>共通名</b> </td> 
   <td colname="col2"> sc-ur-query(am)フィールドは、このシンプルディメンションに使用され、特定のサーバーの最後の空白以外の値です。 監視対象のサーバの共通名が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)フィールドは、指定したサーバーの最後の行の値を示すシンプルディメンションに使用されます。 このディメンションは、サーバーのコンポーネントをチェックし、正しく機能していることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのコンポーネント</b> </td> 
   <td colname="col2"> Crossrows変換は、cs-uri-query(ao)のLast Row値を受け取り、x-components-in-errorフィールドにコピーします。 この多対多ディメンションは、監視対象のサーバーでエラーが発生したコンポーネントを表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">cs-uri-query(c)値が環境IDに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルディメンションは、サーバーが正しく設定されている場合は、実行中の環境を表示します。 <p><p>注意： このディメンションは、insight_monitor_agent.cfgに設定されます。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデケイ秒</b> </td> 
   <td colname="col2"> この数値ディメンションでは、x-estimated-sweep-dekasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値（寸法をより合理的にサイズ設定するためにスイープ測定の解像度を低くした値）です。 <p><p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2"> x-last-pingは、（数値ディメンションのサイズ制約に対応するために）x-unixtimeを10で割る値です。 Last Pingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性をログに記録した時間を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(i)値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 このディメンションは、監視対象のシステム内のサーバーの平均負荷の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(o)値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 このディメンションは、ページファイルのメモリ使用量の割合の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(ag)値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(ag)値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 このディメンションは、各サーバーの物理メモリ使用率の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 このディメンションは、各サーバーのクエリーメモリ使用率の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(q)値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 これは、特定のサーバーのネットワーク接続数を示すために使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間（100秒）</b> </td> 
   <td colname="col2"> このディメンションは、ポーリング待ち時間の計算に使用されます。 cs-uri-query(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centisecondsフィールドにコピーします。 これは、特定のサーバーの最後の行を取る数値ディメンションです。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェックの成功</b> </td> 
   <td colname="col2"> これは、特定のサーバーのLast Rowのcs-uri-query(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2"> cs-uri-query(an)値の最後の行がx-temp-db-space-percentageフィールドにコピーされます。 これは、特定のサーバー上で使用される一時DB領域の割合の計算に使用される数値ディメンションです。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insightのバージョン</b> </td> 
   <td colname="col2"> このシンプルディメンションには、cs-uri-query(ab)値が使用されます。 サーバーの最後の空白以外の値です。 これにより、各サーバーで実行されているData Workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供する単語をグループ化します。 <p>注意： このディメンションは、insight_monitor_agent.cfgに設定されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> Data Workbenchのプロファイル監視プロファイルに含まれる指標と、その派生方法を以下に示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>全体的な容量</b> </td> 
   <td colname="col2"> これは、「容量サイズ」指標に2を掛け、「容量行」指標を3で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> これは、各サーバの容量行の割合の合計をサーバ指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズ</b> </td> 
   <td colname="col2"> これは、各サーバの容量サイズの割合の合計をサーバ指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェック</b> </td> 
   <td colname="col2"> これは、コンポーネントチェックの成功が1に等しいサーバーの数を、サービスがDPUまたはFSUであるサーバーで割って、すべて100を掛けた値（割合）です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」</b> </td> 
   <td colname="col2"> ディスク指標は、各サーバのディスク使用率の合計をサーバ指標で割って計算されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープ時間（分）</b> </td> 
   <td colname="col2"> これは、各サーバーの推定スイープデーケコンドの合計をサーバー指標で割った値で、Estimated Sweep Dekasecondsが0より大きい場合はすべて6で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Last Ping Time</b> </td> 
   <td colname="col2"> 各ブロックの最後のpingの合計をブロックで割って、10を掛けた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> これは、各サーバーの読み込み平均をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイル</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリページファイルの割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリ物理割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリ</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリクエリの割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、各サーバーのネットワーク接続の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間ミリ秒</b> </td> 
   <td colname="col2"> これは、各サーバーのポーリング待ち時間のセンチ秒数の合計をサーバー指標で割った値で、すべて10を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック</b> </td> 
   <td colname="col2"> これは、クイックチェックの成功が1に等しいサーバーの数をサーバー指標で割った値で、すべて100を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> これは、各サーバの1つの合計、または監視対象サーバの合計数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB</b> </td> 
   <td colname="col2"> これは、各サーバーの一時DB領域の割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>

