---
description: 次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。
solution: Analytics
title: Data Workbench履歴プロファイルのディメンション
topic: Data workbench
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench履歴プロファイルのディメンション{#dimensions-in-the-data-workbench-historic-profile}

次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。

## Data Workbench履歴プロファイルのディメンション {#section-96f1b64f5cb84411b630f97f227d888d}

次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2">この設定で可算となるのはこれだけで、すべてのディメンションのルートです。 ブロックはサーバーと見なすことができます。 x-trackingidフィールドを使用しています。 <p>注意： ブロックIDは、サーバ名とホスト名のハッシュです。したがって、プロファイルごとに1つのサーバに約1ブロックが存在します。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> これは、Block可算から構築された可算ディメンションです。 プロファイル内の各データ行は、監視エージェントからのpingです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告の重大</b> </td> 
   <td colname="col2"> cs-uri-query(ad)値から構築された数値ディメンション。 cs-uri-query(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートダウン</b> </td> 
   <td colname="col2"> cs-uri-query(ac)値から構築された数値ディメンション。 これはPingレベルで構築され、cs-uri-query(a)が「1」に一致するという条件が付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告</b> </td> 
   <td colname="col2"> cs-uri-query(ae)値から構築された数値ディメンション。 cs-uri-query(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任意のプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)値から構築された数値ディメンション。 cs-uri-query(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に四捨五入されます。 cs-uri-query(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>生産能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r)値から構築された数値ディメンション。 cs-uri-query(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n)値から構築された数値ディメンション。 cs-uri-query(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)値から構築されたシンプルディメンション。 これはPingレベルで構築され、cs-uri-query(a)が"1"に一致することを条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのコンポーネント</b> </td> 
   <td colname="col2"> cs-uri-query(ao)は、区切り文字「|」で分割され、x-components-in-errorフィールドにコピーされます。 x-components-in-errorフィールドから作成された多対多ディメンション。 Pingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェック秒数</b> </td> 
   <td colname="col2"> cs-uri-query(l)値から構築された数値ディメンション。 cs-uri-query(k)が空でないというpingレベル条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(k)値から構築されたシンプルディメンション。 cs-uri-query(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディメンションGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)がx-dimension-gbigabitesフィールドにコピーされます。 x-dimension-gbigatesフィールドは、「2」と一致するcs-uri-query(a)に基づいて、このシンプルディメンションのユーザーです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」の使用率</b> </td> 
   <td colname="col2"> これらの数値ディメンションは、cs-uri-query(ah, ai, aj, ak, al)値から設定されます。 これらはPingレベルで構築され、cs-uri-query(a)が"1"に一致し、cs-uri-query(k)が空ではないことに基づいて条件が付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデケイ秒</b> </td> 
   <td colname="col2"> この数値ディメンションでは、x-estimated-sweep-dekasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値（寸法をより合理的にサイズ設定するためにスイープ測定の解像度を低くした値）です。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MegaBytes/Minute</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputにある場合、この数値ディメンションの値には、システムがデータを入力する1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MegaBytes/Minute</b> </td> 
   <td colname="col2">このディメンションには、cs-uri-query(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Mergeに含まれる場合、この数値ディメンションの値には、システムがマージされる1分あたりのMB数が表示されます。 <p><p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">このディメンションにはcs-uri-query(bg)値が使用されます。 値を1000で割り、最も近い整数に四捨五入します。 この数値ディメンションの値には、データセット内のフィールドで使用されている領域の量が表示されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> cs-uri-query(x)値からPingレベルで構築されたシンプルディメンション。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Host</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2"> x-unixtimeフィールドがx-last-pingにコピーされ、10で割られて、基数が減少します。 数値ディメンションは、ブロックレベルで構築され、x-last-pingフィールドを使用します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(i)値に対してLast Rowを使用する数値ディメンションです。 cs-uri-query(k)が空でない場合に条件が設定されます。 このディメンションは、監視対象のシステム内のサーバーの平均負荷の計算に使用されます。 <p><p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">cs-uri-query(be)値は、Pingレベルで構築されたこの数値ディメンションに使用されます。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-query(o)値を使用するNumericディメンションです。 cs-uri-query(k)が空でないことと、cs-uri-query(a)が「1」に一致することに基づいて条件が付けられます。 このディメンションは、ページファイルのメモリ使用量の割合の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2">これは、Pingレベルで構築されたcs-uri-query(ag)値を使用するNumericディメンションです。 cs-uri-query(k)が空でないことと、cs-uri-query(a)が"1"に一致することに対して条件が付けられます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理割合</b> </td> 
   <td colname="col2">これは、Pingレベルで構築されたcs-uri-query(ag)値を使用するNumericディメンションです。 cs-uri-query(k)が空でないことと、cs-uri-query(a)が"1"に一致することに対して条件が付けられます。 このディメンションは、各サーバーの物理メモリ使用率の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、Pingレベルでcs-uri-query(s)値を使用するNumericディメンションです。 cs-uri-query(k)が空でなく、cs-uri-query(a)が「1」に一致する場合に条件付けされます。 このディメンションは、各サーバーのクエリーメモリ使用率の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-query(q)値を使用するNumericディメンションです。 cs-uri-query(k)が空でなく、cs-uri-query(a)が「1」に一致する場合に条件付けされます。 これは、特定のサーバーのネットワーク接続数を示すために使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出力行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)値を100000で割り、x-output-rowsフィールドにコピーして、ディメンションのサイズを小さくします。 X-output-rowsは、Pingレベルで構築された数値ディメンションで使用され、cs-uri-query(a)が"2"に一致するという条件が付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>PingタイプID</b> </td> 
   <td colname="col2"> Pingレベルでcs-uri-query(a)値を使用して構築されたシンプルディメンション。 これは、どのようなPingが記録されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間（100秒）</b> </td> 
   <td colname="col2">cs-uri-query(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centisecondsフィールドにコピーします。 これはPingレベルで構築されたNumericディメンションで、cs-uri-query(k)が空ではなく、cs-uri-query(a)が"1"/に一致することが条件付けられます。このディメンションは、ポーリング待ち時間の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)値は、Pingレベルで構築されたこのシンプルディメンションに使用されます。 cs-uri-query(bb)が空ではなく、cs-uri-query(a)が「2」の処理モードIDと一致すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは非表示になり、クライアント側のディメンションの処理モードでフレンドリ値を使用して再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> cs-uri-query(ba)値は、このシンプルディメンションに使用され、Pingレベルで構築されます。 このディメンションには、現在監視中のプロファイルの名前が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック秒数</b> </td> 
   <td colname="col2"> この数値ディメンションには、cs-uri-query(h)値が使用されます。 cs-uri-query(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェックの成功</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-query(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>リアルタイム処理の割合</b> </td> 
   <td colname="col2"> Pingレベルで構築されたcs-uri-query(t)値を使用する数値ディメンション。 cs-uri-query(a)が「1」に一致することを条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も背後のソース</b> </td> 
   <td colname="col2"> Pingレベルで構築されたcs-uri-query(bl)値から構築されたシンプルディメンション。 このディメンションには、データソースとの最後の接触が発生した日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2">Pingレベルで構築されたcs-uri-query(an)値を使用して構築された数値ディメンション。 cs-uri-query(k)が空ではなく、cs-uri-query(a)が「1」と一致することが条件付けられます。 特定のサーバー上でのTemp DBの使用済み領域の割合の計算に使用されます。 <p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2">cs-uri-query(bf)値がこの数値ディメンションに使用されます。 Pingレベルで構築されます。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p><p>注意： このディメンションは、指標に平均化された場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchのバージョン</b> </td> 
   <td colname="col2"> このシンプルディメンションには、cs-uri-query(ab)値が使用されます。 これはPingレベルで構築され、cs-uri-query(ab)が空ではなく、cs-uri-query(a)が「1」に一致することが条件付きです。 これにより、各サーバーで実行されているData Workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchバージョンメジャー</b> </td> 
   <td colname="col2"> cs-uri-query(ab)値が分割され、メジャーリリース値がx-insight-version-majorフィールドにコピーされます。 これは、Pingレベルで構築され、x-insight-version-majorが空でないこと、およびcs-uri-query(a)が"1"に一致することを条件付けられたSimple Dimensionです。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->

