---
description: 次のディメンションは、Data WorkbenchのServer Statusプロファイルで使用できます。
title: Data Workbench サーバーステータスプロファイルのディメンション
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench サーバーステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-server-status-profile}

次のディメンションは、Data WorkbenchのServer Statusプロファイルで使用できます。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> x-trackingidフィールドを基に作成されたこの可算ディメンションは、Data Workbenchを現在実行しているサーバーを表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エージェントのバージョン</b> </td> 
   <td colname="col2"> このシンプルなDimensionにはcs-uri-query(af)値が使用されます。 サーバーの空白でない最後の値です。 実行中の監視エージェントのバージョンのビルド日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>すべてのプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)フィールドは、このNumericDimensionに使用されます。これは、特定のサーバーの最後の行の値で、cs-uri-query(k)に基づく条件は空ではありません。 このディメンションは、プロファイルが再処理であるかどうかを示すために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r)フィールドは、このNumericDimensionに使用されます。これは、特定のサーバのLast Rowの値で、cs-uri-query(k)の条件は空ではありません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n)フィールドは、このNumericDimensionに使用されます。これは、特定のサーバの最後の行の値で、cs-uri-query(k)の条件は空ではありません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>共通名</b> </td> 
   <td colname="col2"> sc-ur-query(am)フィールドは、この単純Dimensionに使用され、特定のサーバーの「最後の空白以外」の値です。 監視対象のサーバの共通名が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)フィールドは、このシンプルDimensionに使用され、特定のサーバの最後の行の値です。 このディメンションは、サーバーのコンポーネントをチェックして、正しく機能していることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのあるコンポーネント</b> </td> 
   <td colname="col2"> Crossrows変換は、cs-uri-query(ao)のLast Row値を取得し、x-components-in-errorフィールドにコピーします。 この多対多ディメンションは、監視対象のサーバーでエラーが発生したコンポーネントを表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">cs-uri-query(c)値が環境IDに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境（正しく設定されている場合）を表示します。 <p><p>注意： このディメンションは、 insight_monitor_agent.cfgで設定します。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデーカ秒</b> </td> 
   <td colname="col2"> この数値Dimensionでは、x-estimated-sweep-dekasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値です（寸法をより合理的なサイズにするためにスイープ測定の解像度を低くした値）。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のping</b> </td> 
   <td colname="col2"> x-last-pingは、x-unixtimeを10で除算します（数値ディメンションのサイズ制約に対応するため）。 最後のpingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時刻を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(i)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 このディメンションは、監視対象のシステムのサーバーの平均負荷を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(o)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(ag)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(ag)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 このディメンションは、各サーバーのクエリメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(q)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 これは、特定のサーバーのネットワーク接続数を示すために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング遅延（百分秒）</b> </td> 
   <td colname="col2"> このディメンションは、ポーリング待ち時間の計算に使用されます。 cs-uri-query(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centicesフィールドにコピーします。 これは、特定のサーバーの最後の行を取る数値ディメンションです。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェックの成功</b> </td> 
   <td colname="col2"> これは、特定のサーバーの最後の行のcs-uri-query(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2"> cs-uri-query(an)値の最後の行がx-temp-db-space-percentageフィールドにコピーされます。 これは数値Dimensionで、特定のサーバー上の使用済み一時DB領域の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insightバージョン</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(ab)値が使用されます。 サーバーの空白でない最後の値です。 各サーバーで実行されているData Workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供するグループ化語。 <p>注意： このディメンションは、 insight_monitor_agent.cfgで設定します。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次に、Data Workbenchのプロファイル監視プロファイルに含まれる指標と、それらの派生方法を示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>全体の処理能力</b> </td> 
   <td colname="col2"> これは、「処理能力サイズ」指標に2を加え、容量行指標を3で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行</b> </td> 
   <td colname="col2"> これは、各サーバーの容量行の割合をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力サイズ</b> </td> 
   <td colname="col2"> これは、各サーバーの容量サイズの割合をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントの確認</b> </td> 
   <td colname="col2"> これは、コンポーネントチェックの成功が1に等しいサーバーの数を、サービスがDPUまたはFSUのサーバーで割った値に、すべてが100を掛けた値です（パーセントにします）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」</b> </td> 
   <td colname="col2"> ディスクの指標は、各サーバーのディスク使用率の合計をサーバーの指標で割って計算されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープ（分）</b> </td> 
   <td colname="col2"> これは、各サーバの推定スイープデーカ秒の合計を、 Estimated Sweepデーカ秒が0より大きいサーバー指標で割った値で、すべて6で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>前回のping時間</b> </td> 
   <td colname="col2"> 各ブロックの最後のpingの合計をブロックで割って、10を掛けた値。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Load</b> </td> 
   <td colname="col2"> これは、各サーバーの負荷平均をサーバー指標で割った値です。 </td> 
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
   <td colname="col2"> これは、各サーバーのメモリクエリの割合の合計を、サーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、各サーバーのネットワーク接続の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポール待ち時間（ミリ秒）</b> </td> 
   <td colname="col2"> これは、各サーバーのポーリング待ち時間の百分率の合計をサーバー指標で割った値です。すべてに10を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック</b> </td> 
   <td colname="col2"> これは、クイックチェックの成功が1に等しいサーバーの数をサーバー指標で割った値で、すべてに100を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> これは、各サーバの合計または監視対象サーバの合計数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB</b> </td> 
   <td colname="col2"> これは、各サーバーの一時DB領域の割合の合計を、サーバー指標で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>
