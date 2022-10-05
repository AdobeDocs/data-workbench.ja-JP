---
description: 次のディメンションは、Data Workbench の履歴プロファイルで使用できます。
title: Data Workbench 履歴プロファイルのディメンション
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 履歴プロファイルのディメンション{#dimensions-in-the-data-workbench-historic-profile}

{{eol}}

次のディメンションは、Data Workbench の履歴プロファイルで使用できます。

## Data Workbench 履歴プロファイルのディメンション {#section-96f1b64f5cb84411b630f97f227d888d}

次のディメンションは、Data Workbench の履歴プロファイルで使用できます。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2">この設定で可算となるのはこれだけで、すべてのディメンションのルートです。 ブロックは、サーバーと見なすことができます。 x-trackingid フィールドを使用しています。 <p>注意：ブロック ID は、サーバー名とホスト名のハッシュなので、プロファイルごとにサーバーごとに約 1 ブロック存在します。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> これは、ブロック可算から作成された可算ディメンションです。 プロファイル内のデータの各行は、監視エージェントからの ping です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートの重大</b> </td> 
   <td colname="col2"> cs-uri-query(ad) 値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致するという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートダウン</b> </td> 
   <td colname="col2"> cs-uri-query(ac) 値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致する条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告</b> </td> 
   <td colname="col2"> cs-uri-query(ae) の値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致するという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>すべてのプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa) 値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致し、cs-uriquery(k) が空でないという Ping レベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi) は、x-as-of-delay-minutes フィールドに配置され、最も近い分に丸められます。 cs-uri-query(a) が"1"に一致するという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r) 値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致し、cs-uriquery(k) が空でないという Ping レベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n) 値から構築された数値Dimension。 cs-uri-query(a) が"1"に一致し、cs-uriquery(k) が空でないという Ping レベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェック成功</b> </td> 
   <td colname="col2"> cs-uri-query(v) 値から構築された単純なDimension。 これは Ping レベルで構築され、cs-uri-query(a) が"1"に一致するように条件が設定されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのコンポーネント</b> </td> 
   <td colname="col2"> cs-uri-query(ao) は、「|」区切り文字で分割され、x-components-in-error フィールドにコピーされます。 多対多Dimensionx-components-in-error フィールドから作成した値。 Ping レベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェック秒数</b> </td> 
   <td colname="col2"> cs-uri-query(l) 値から構築された数値Dimension。 cs-uri-query(k) が空でないという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェック成功</b> </td> 
   <td colname="col2"> cs-uri-query(k) 値から構築された単純なDimension。 cs-uri-query(a) が"1"に一致するという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc) は、x-dimension-gigbates フィールドにコピーされます。 x-dimension-gabigates フィールドは、「2」に一致する cs-uri-query(a) に基づいて、このシンプルDimensionのユーザーです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスクの「x」使用率</b> </td> 
   <td colname="col2"> これらの数値Dimensionは、cs-uri-query(ah, ai, aj, ak, al) 値から設定されます。 これらは Ping レベルで構築され、cs-uri-query(a) が"1"に一致し、cs-uri-query(k) が空ではないことに基づいて条件付けされます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデーケ秒</b> </td> 
   <td colname="col2"> この「数値」Dimensionでは、x-estimated-sweep-dekaseconds フィールドが使用されます。 これは、サーバの推定スイープ時間を 10 で割った値です（寸法をより合理的にサイズにするためにスイープ測定の解像度を低くした値）。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>高速入力メガバイト/分</b> </td> 
   <td colname="col2"> cs-uri-query(bj) 値がこのディメンションに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットが高速入力の場合、この数値Dimensionの値には、システムがデータを入力する時点の MB/分が表示されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1 分あたりの高速マージメガバイト数</b> </td> 
   <td colname="col2">cs-uri-query(bk) 値がこのディメンションに使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットが高速結合の場合、この数値Dimensionの値には、システムが結合する時点の MB/分が表示されます。 <p><p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>フィールド GigaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bg) 値がこのディメンションに使用されます。 値を 1000 で割り、最も近い整数に丸めます。 この数値Dimensionの値には、データセット内のフィールドが使用している容量が表示されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> cs-uri-query(x) 値から Ping レベルで構築された単純なDimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> cs-uri-query(b) 値がこのディメンションに使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後の Ping</b> </td> 
   <td colname="col2"> x-unixtime フィールドが x-last-ping にコピーされ、基数を 10 で割って減らされます。 数値Dimensionは、ブロックレベルで作成され、x-last-ping フィールドを使用します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーの cs-uri-query(i) 値に対して最後の行を使用する数値ディメンションです。 cs-uri-query(k) が空でないことに基づいて条件付けされます。 このディメンションは、監視対象のシステム内のサーバーの平均負荷を計算するために使用されます。 <p><p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">cs-uri-query(be) 値は、この数値ディメンションに使用され、Ping レベルで作成されます。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、cs-uri-query(o) 値を使用する Numeric ディメンションで、Ping レベルで作成されます。 cs-uri-query(k) が空でないことと、cs-uri-query(a) が「1」に一致することに基づいて条件が設定されます。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2">これは、cs-uri-query(ag) 値を使用する Numeric ディメンションで、Ping レベルで構築されます。 cs-uri-query(k) が空でなく、cs-uri-query(a) が"1"に一致することで条件付けされます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリの物理的な割合</b> </td> 
   <td colname="col2">これは、cs-uri-query(ag) 値を使用する Numeric ディメンションで、Ping レベルで構築されます。 cs-uri-query(k) が空でなく、cs-uri-query(a) が"1"に一致することで条件付けされます。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、Ping レベルで cs-uri-query 値を使用する数値ディメンションです。 cs-uri-query(k) が空でなく、cs-uri-query(a) が"1"に一致することに基づいて条件が設定されます。 このディメンションは、各サーバーのクエリメモリ使用量の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、Ping レベルで構築された cs-uri-query(q) 値を使用する Numeric ディメンションです。 cs-uri-query(k) が空でなく、cs-uri-query(a) が"1"に一致することに基づいて条件が設定されます。 これは、特定のサーバーに対するネットワーク接続の数を示すために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出力行</b> </td> 
   <td colname="col2"> cs-uri-query(bh) の値を100000で割り、x-output-rows フィールドにコピーして、ディメンションのサイズを小さくします。 X-output-rows は、cs-uri-query(a) が"2"に一致する条件を Ping レベルで構築された数値Dimensionで使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping タイプ ID</b> </td> 
   <td colname="col2"> cs-uri-query(a) 値を Ping レベルで使用して構築された単純なDimension。 これは、どのような Ping が記録されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング遅延（百分率）</b> </td> 
   <td colname="col2">cs-uri-query(m) の値を 10 で割って、ディメンションサイズを小さくし、x-poll-latency-centices フィールドにコピーします。 これは、cs-uri-query(k) が空ではなく、cs-uri-query(a) が「1」/と一致するという条件付きの Ping レベルで構築された数値ディメンションです。このディメンションは、ポーリング待ち時間の計算に使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モード ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb) 値は、Ping レベルで構築されたこのシンプルDimensionに使用されます。 cs-uri-query(bb) が空ではなく、cs-uri-query(a) が「2」処理モード ID と一致することで、システムの処理モード (Fast Input、Fast Merge、Real Time) を確認できます。 <p>注意：このディメンションは、非表示になり、クライアント側のディメンションの処理モードでわかりやすい値で再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> cs-uri-query(ba) 値は、このシンプルなDimensionに使用され、Ping レベルで構築されます。 このディメンションは、現在監視中のプロファイルの名前を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック秒</b> </td> 
   <td colname="col2"> cs-uri-query(h) 値は、この数値Dimensionに使用されます。 cs-uri-query(a) が"1"に一致するという条件を Ping レベルで構築します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック成功</b> </td> 
   <td colname="col2"> これは、Ping レベルで構築された cs-uri-query(g) 値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>リアルタイム処理の割合</b> </td> 
   <td colname="col2"> Ping レベルで作成された cs-uri-query(t) 値を使用する数値Dimension。 cs-uri-query(a) が"1"に一致するように条件付けされます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も遠い後のソース</b> </td> 
   <td colname="col2"> Ping レベルで構築された cs-uri-query(bl) 値から構築された単純なDimension。 このディメンションは、データソースとの最後の連絡が発生した日時を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時 DB 領域の割合</b> </td> 
   <td colname="col2">cs-uri-query(an) 値を使用して構築された数値Dimension。Ping レベルで構築されます。 cs-uri-query(k) が空ではなく、cs-uri-query(a) が"1"に一致するように条件付けされます。 特定のサーバー上の使用済み Temp DB 領域の割合を計算するために使用されます。 <p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2">cs-uri-query(bf) 値は、この数値ディメンションに使用されます。 Ping レベルで構築されます。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p><p>注意：このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchバージョン</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(ab) 値が使用されます。 cs-uri-query(ab) が空でなく、cs-uri-query(a) が"1"に一致することを Ping レベルで構築し、条件を設定します。 各サーバーで実行されている Data Workbench サーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchバージョンのメジャー</b> </td> 
   <td colname="col2"> cs-uri-query(ab) の値が分割され、メジャーリリース値が x-insight-version-major フィールドにコピーされます。 これは、x-insight-version-major が空でなく、cs-uri-query(a) が"1"に一致するという条件が Ping レベルで構築されたシンプルなDimensionです。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
