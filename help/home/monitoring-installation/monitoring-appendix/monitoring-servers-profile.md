---
description: 次のディメンションは、Data Workbenchサーバーのステータスプロファイルで使用できます。
title: Data Workbench サーバーステータスプロファイルのディメンション
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench サーバーステータスプロファイルのディメンション{#dimensions-in-the-data-workbench-server-status-profile}

次のディメンションは、Data Workbenchサーバーのステータスプロファイルで使用できます。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> この可算ディメンションは、x-trackingidフィールドから構築され、Data Workbenchが現在実行されているサーバーを表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エージェントのバージョン</b> </td> 
   <td colname="col2"> この単純なDimensionには、cs-uri-クエリ(af)値が使用されます。 サーバーの最後の空白以外の値です。 これにより、実行中の監視エージェントのバージョンのビルド日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-クエリ(aa)フィールドは、この数値Dimensionに使用されます。これは、cs-uri-クエリ(k)に条件を付ける、特定のサーバーの最後の行の値です。 このディメンションは、再処理中のプロファイルがあるかどうかを示すために使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>生産能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-クエリ(r)フィールドは、この数値Dimensionに使用されます。これは、cs-uri-クエリ(k)に条件を付ける、特定のサーバーの最後の行の値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-クエリ(n)フィールドは、この数値Dimensionに使用されます。これは、cs-uri-クエリ(k)に条件を付ける、特定のサーバーの最後の行の値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>共通名</b> </td> 
   <td colname="col2"> sc-ur-クエリ(am)フィールドは、この単純なDimensionに使用されます。この値は、特定のサーバーの最後の空白以外の値です。 監視対象のサーバの共通名が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-クエリ(v)フィールドは、この単純なDimensionに使用されます。これは、特定のサーバーの最後の行の値です。 このディメンションは、サーバーのコンポーネントをチェックして、正しく機能していることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのあるコンポーネント</b> </td> 
   <td colname="col2"> Crossrows変換は、cs-uri-error(ao)のLast Row値を受け取って、x-components-in-errorフィールドにコピーします。 この多対多ディメンションは、監視対象のサーバーでエラーが発生したコンポーネントを表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">環境IDにはcs-uri-クエリ(c)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 このシンプルなDimensionは、サーバーが実行されている環境を表示します（正しく設定されている場合）。 <p><p>注意： このディメンションは、insight_monitor_agent.cfg内で設定されます。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデカス秒</b> </td> 
   <td colname="col2"> この数値Dimensionでは、x-estimated-sweep-decasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値です（寸法をより適正なサイズにするために、スイープ測定の解像度を低くした値）。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2"> x-last-pingは、x-unixtimeを10で割る（数値ディメンションのサイズ制約に対応する）ことです。 Last Pingは、特定のブロックの最後の行で、監視エージェントが最後にシステムの正常性を記録した時刻を表します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(i)値に対して、Last Rowを使用する数値ディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 このディメンションは、監視対象システム内のサーバーの平均負荷の計算に使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(o)値に対して、Last Rowを使用する数値ディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(ag)値に対してLast Rowを使用するNumericディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリの物理的割合</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(ag)値に対してLast Rowを使用するNumericディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ値に対して、Last Rowを使用する数値ディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 このディメンションは、各サーバーのクエリメモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(q)値に対して、Last Rowを使用する数値ディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 これは、特定のサーバーのネットワーク接続数を示すために使用します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間（センチ秒）</b> </td> 
   <td colname="col2"> このディメンションは、ポーリング待ち時間の計算に使用されます。 cs-uri-クエリ(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centicedsフィールドにコピーします。 これは、特定のサーバーのLast Rowを受け取るNumericディメンションです。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック成功</b> </td> 
   <td colname="col2"> これは、特定のサーバーのLast Rowのcs-uri-クエリ(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2"> cs-uri-クエリ(an)値の最後の行がx-temp-db-space-percentageフィールドにコピーされます。 これは、特定のサーバー上で使用されている一時DB領域の割合を計算するために使用される数値Dimensionです。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insightバージョン</b> </td> 
   <td colname="col2"> この単純なDimensionには、cs-uri-クエリ(ab)値が使用されます。 サーバーの最後の空白以外の値です。 これにより、各サーバーで実行されているdata workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> 結果のデータセットをフィルタリングする別の方法を提供するグループ化語。 <p>注意： このディメンションは、insight_monitor_agent.cfg内で設定されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>指標</b> </td> 
   <td colname="col2"> 次のリストには、data workbenchプロファイルの監視プロファイルに含まれる指標とその派生方法が示されています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量全体</b> </td> 
   <td colname="col2"> これは、「Capacity Size」指標に2を掛け、「Capacity Row」指標を3で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> これは、各サーバーの容量行の割合の合計をサーバー指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズ</b> </td> 
   <td colname="col2"> これは、各サーバの容量サイズの割合の合計を、サーバ指標で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェック</b> </td> 
   <td colname="col2"> 「Component Check Success」が1に等しいサーバーの数を、ServiceがDPUまたはFSUのサーバーで割った値です。すべて100を乗算して100を割った値です（割合を算出する場合）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」</b> </td> 
   <td colname="col2"> ディスク指標は、各サーバーのディスク使用率の合計をサーバー指標で割って計算されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープ時間（分）</b> </td> 
   <td colname="col2"> これは、各サーバーの推定スイープデカスコンドの合計をサーバー指標で割った値です。この値を、推定スイープデカスコンドが0より大きい場合は、すべて6で割った値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最終Ping時間</b> </td> 
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
   <td colname="col2"> これは、各サーバーのポーリング待ち時間のセンチ秒数の合計をサーバー指標で割った値です。すべて10を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック</b> </td> 
   <td colname="col2"> クイックチェックの成功が1に等しいサーバーの数をサーバー指標で割った値です。すべて100を掛けた値です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>サーバー</b> </td> 
   <td colname="col2"> これは、各サーバの1つの合計、または監視対象サーバの合計数です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB</b> </td> 
   <td colname="col2"> これは、各サーバーの一時DB領域の割合の合計を、サーバー指標で割った値です。 </td> 
  </tr> 
 </tbody> 
</table>
