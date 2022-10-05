---
description: 次のディメンションは、Data Workbench の Server Status プロファイルで使用できます。
title: Data Workbench サーバーステータスプロファイルのディメンション
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench サーバーステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

次のディメンションは、Data Workbench の Server Status プロファイルで使用できます。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> x-trackingid フィールドから作成され、この可算ディメンションは、Data Workbench を現在実行中のサーバーを表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エージェントのバージョン</b> </td> 
   <td colname="col2"> このシンプルDimensionには cs-uri-query(af) 値が使用されます。 サーバーの最後の空白以外の値です。 実行中の監視エージェントのバージョンのビルド日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>すべてのプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa) フィールドは、この数値Dimensionで使用され、cs-uri-query(k) の条件が空でない、特定のサーバの最後の行の値です。 このディメンションは、プロファイルが再処理であるかどうかを示すために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r) フィールドは、この数値Dimensionで使用され、指定したサーバの最後の行の値で、cs-uri-query(k) の条件は空ではありません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n) フィールドは、この数値Dimensionで使用され、cs-uri-query(k) の条件が空でない、指定したサーバの最後の行の値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>共通名</b> </td> 
   <td colname="col2"> sc-ur-query(am) フィールドは、このシンプルDimensionに使用され、特定のサーバーの Last Nonblank 値の値です。 監視対象のサーバーの共通名が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェック成功</b> </td> 
   <td colname="col2"> cs-uri-query(v) フィールドは、このシンプルなDimensionに使用され、特定のサーバの最後の行の値です。 このディメンションは、サーバーのコンポーネントをチェックして、正しく機能していることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのコンポーネント</b> </td> 
   <td colname="col2"> Crossrows 変換は、cs-uri-query(ao) の Last Row 値を取得し、x-components-in-error フィールドにコピーします。 この多対多ディメンションは、監視対象のサーバーでエラーになったコンポーネントを表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">cs-uri-query(c) 値は環境 ID に使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境を表示します（適切に設定されている場合）。 <p><p>注意：このディメンションは、 insight_monitor_agent.cfg で設定されます。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデーケ秒</b> </td> 
   <td colname="col2"> この「数値」Dimensionでは、x-estimated-sweep-dekaseconds フィールドが使用されます。 これは、サーバの推定スイープ時間を 10 で割った値です（寸法をより合理的にサイズにするためにスイープ測定の解像度を低くした値）。 <p><p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> cs-uri-query(b) 値がこのディメンションに使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後の Ping</b> </td> 
   <td colname="col2"> x-last-ping は、x-unixtime を 10 で割る値です（数値ディメンションのサイズ制約に対応するため）。 「最後の ping 」は、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時点を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(i) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 このディメンションは、監視対象のシステム内のサーバーの平均負荷を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(o) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(ag) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリの物理的な割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(ag) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 このディメンションは、各サーバーのクエリメモリ使用量の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(q) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 これは、特定のサーバーに対するネットワーク接続の数を示すために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング遅延（百分率）</b> </td> 
   <td colname="col2"> このディメンションは、ポーリング待ち時間の計算に使用されます。 cs-uri-query(m) の値を 10 で割って、ディメンションサイズを小さくし、x-poll-latency-centices フィールドにコピーします。 これは、特定のサーバーの最後の行を取得する数値ディメンションです。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック成功</b> </td> 
   <td colname="col2"> これは、特定のサーバーの最後の行の cs-uri-query(g) 値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時 DB 領域の割合</b> </td> 
   <td colname="col2"> cs-uri-query(an) 値の最後の行が x-temp-db-space-percentage フィールドにコピーされます。 これは数値Dimensionで、特定のサーバー上の使用済み Temp DB 領域の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight バージョン</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(ab) 値が使用されます。 サーバーの最後の空白以外の値です。 各サーバーで実行されている Data Workbench サーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供する単語をグループ化します。 <p>注意：このディメンションは、 insight_monitor_agent.cfg で設定されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次に、Data Workbench のプロファイル監視プロファイルに含まれる指標と、その派生方法を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量全体</b> </td> 
   <td colname="col2"> これは、「処理能力サイズ」指標に 2 倍、「処理能力行」指標を 3 で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行</b> </td> 
   <td colname="col2"> これは、各サーバーの容量行の割合をサーバー指標で割った合計です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズ</b> </td> 
   <td colname="col2"> これは、各サーバーの容量サイズの割合をサーバー指標で割った合計です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェック</b> </td> 
   <td colname="col2"> これは、コンポーネントチェック成功が 1 に等しいサーバの数を、サービスが DPU または FSU であるサーバで割った数です。すべてに 100 を掛けた数です（割合にします）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」</b> </td> 
   <td colname="col2"> ディスク指標は、各サーバのディスク使用率の合計をサーバー指標で割って計算されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープ分</b> </td> 
   <td colname="col2"> これは、各サーバの推定スイープデーケ秒の合計です。この値を、Estimated Sweep デーケ秒が 0 より大きい場合の Servers 指標で割り、すべて 6 で割ります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>前回の Ping 時間</b> </td> 
   <td colname="col2"> 各ブロックの最後の ping の合計をブロックで割って、10 を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> これは、各サーバーの負荷平均を Servers 指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイル</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリページファイルの割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリ物理割合の合計で、サーバー指標で割られます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリ</b> </td> 
   <td colname="col2"> これは、各サーバーのメモリクエリの割合の合計を、サーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、各サーバーのネットワーク接続の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間ミリ秒</b> </td> 
   <td colname="col2"> これは、各サーバーのポーリング待ち時間の百分率の合計です。この値をサーバー指標で割り、すべて 10 を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック</b> </td> 
   <td colname="col2"> これは、クイックチェックの成功が 1 に等しいサーバーの数をサーバー指標で割った値で、すべてに 100 を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> これは、各サーバの合計、または監視対象サーバの合計数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時 DB</b> </td> 
   <td colname="col2"> これは、各サーバーの一時 DB 領域の割合の合計で、サーバー指標で割られます。 </td> 
  </tr> 
 </tbody> 
</table>
