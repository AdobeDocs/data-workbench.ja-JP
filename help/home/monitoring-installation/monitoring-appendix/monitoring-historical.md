---
description: 次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。
title: Data Workbench 履歴プロファイルのディメンション
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 履歴プロファイルのディメンション{#dimensions-in-the-data-workbench-historic-profile}

次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。

## Data Workbench 履歴プロファイルのディメンション {#section-96f1b64f5cb84411b630f97f227d888d}

次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>ブロック</b> </td> 
   <td colname="col2">この設定で可算になるのはこれだけで、すべてのディメンションのルートです。 ブロックは、サーバーと見なすことができます。 x-trackingidフィールドを使用しています。 <p>注意： ブロックIDは、サーバー名とホスト名のハッシュなので、プロファイルごとにサーバーごとに約1ブロックあります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> これは、ブロック可算から作成された可算ディメンションです。 プロファイル内のデータの各行は、監視エージェントからのpingです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートの重大</b> </td> 
   <td colname="col2"> cs-uri-query(ad)値を基に作成された数値Dimension。 cs-uri-query(a)が「1」に一致するという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートダウン</b> </td> 
   <td colname="col2"> cs-uri-query(ac)値から構築された数値Dimension。 cs-uri-query(a)が「1」に一致することを条件に、Pingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告</b> </td> 
   <td colname="col2"> cs-uri-query(ae)値から構築された数値Dimension。 cs-uri-query(a)が「1」に一致するという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>すべてのプロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)値から構築された数値Dimension。 cs-uri-query(a)が「1」に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）</b> </td> 
   <td colname="col2"> cs-uri-query(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に丸められます。 cs-uri-query(a)が「1」に一致するという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-query(r)値から構築された数値Dimension。 cs-uri-query(a)が「1」に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理能力サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-query(n)値から構築された数値Dimension。 cs-uri-query(a)が「1」に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)値から構築されたシンプルなDimension。 これはPingレベルで構築され、cs-uri-query(a)が「1」に一致するように条件が設定されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのあるコンポーネント</b> </td> 
   <td colname="col2"> cs-uri-query(ao)は、「|」区切り文字で分割され、x-components-in-errorフィールドにコピーされます。 多対多Dimensionx-components-in-errorフィールドから作成されたエラー。 pingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェック秒数</b> </td> 
   <td colname="col2"> cs-uri-query(l)値から構築された数値Dimension。 cs-uri-query(k)が空でないという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェックの成功</b> </td> 
   <td colname="col2"> cs-uri-query(k)値から構築されたシンプルなDimension。 cs-uri-query(a)が「1」に一致するという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)は、x-dimension-gigbateフィールドにコピーされます。 x-dimension-gbigateフィールドは、このシンプルDimensionのユーザーで、「2」に一致するcs-uri-query(a)に基づいて条件が設定されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」使用率</b> </td> 
   <td colname="col2"> これらの数値Dimensionは、cs-uri-query(ah, ai, aj, ak, al)値から設定されます。 これらはPingレベルで構築され、cs-uri-query(a)が「1」に一致し、cs-uri-query(k)が空でないことに条件が付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデーカ秒</b> </td> 
   <td colname="col2"> この数値Dimensionでは、x-estimated-sweep-dekasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値です（寸法をより合理的なサイズにするためにスイープ測定の解像度を低くした値）。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>高速入力メガバイト/分</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputに含まれている場合、この数値Dimensionの値には、システムがデータを入力する1分あたりのMB数が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>1分あたりの高速マージメガバイト数</b> </td> 
   <td colname="col2">このディメンションにはcs-uri-query(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Merge This NumericDimensionの値には、システムがマージされる1分あたりのMB数が表示されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">このディメンションにはcs-uri-query(bg)値が使用されます。 値を1000で割り、最も近い整数に丸めます。 この数値Dimensionの値には、データセット内のフィールドで使用されている領域の量が表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> cs-uri-query(x)値からPingレベルで構築されたシンプルなDimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションにはcs-uri-query(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のping</b> </td> 
   <td colname="col2"> x-unixtimeフィールドがx-last-pingにコピーされ、基数を10で割って減らします。 数値Dimensionは、ブロックレベルで作成され、x-last-pingフィールドを使用します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、特定のサーバーのcs-uri-query(i)値の最後の行を使用する数値ディメンションです。 cs-uri-query(k)が空でないことに対応します。 このディメンションは、監視対象のシステムのサーバーの平均負荷を計算するために使用されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ログ読み取りの割合</b> </td> 
   <td colname="col2">cs-uri-query(be)値は、Pingレベルで構築されたこの数値ディメンションに使用されます。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、cs-uri-query(o)値を使用するNumericディメンションで、Pingレベルで作成されます。 空でないcs-uri-query(k)と「1」に一致するcs-uri-query(a)に対して条件が設定されます。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2">これは、cs-uri-query(ag)値を使用するNumericディメンションで、Pingレベルで構築されます。 空でないcs-uri-query(k)と、「1」に一致するcs-uri-query(a)に対して条件が設定されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理割合</b> </td> 
   <td colname="col2">これは、cs-uri-query(ag)値を使用するNumericディメンションで、Pingレベルで構築されます。 空でないcs-uri-query(k)と、「1」に一致するcs-uri-query(a)に対して条件が設定されます。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、Pingレベルでcs-uri-query値を使用する数値ディメンションです。 空でないcs-uri-query(k)と「1」に一致するcs-uri-query(a)に対して条件が設定されます。 このディメンションは、各サーバーのクエリメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-query(q)値を使用する数値ディメンションです。 空でないcs-uri-query(k)と「1」に一致するcs-uri-query(a)に対して条件が設定されます。 これは、特定のサーバーのネットワーク接続数を示すために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出力行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)の値を100000で割り、x-output-rowsフィールドにコピーして、ディメンションのサイズを小さくします。 X-output-rowsは、cs-uri-query(a)が「2」に一致する条件を付け、Pingレベルで構築されたNumericDimensionで使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>PingタイプID</b> </td> 
   <td colname="col2"> cs-uri-query(a)値をPingレベルで使用して構築されたシンプルなDimension。 これは、どのようなpingが記録されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング遅延（百分秒）</b> </td> 
   <td colname="col2">cs-uri-query(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centicesフィールドにコピーします。 これは、Pingレベルで構築された数値ディメンションで、cs-uri-query(k)が空ではなく、cs-uri-query(a)が「1」に一致することを条件とします。このディメンションは、ポーリング待ち時間の計算に使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)値は、Pingレベルで構築されたこのシンプルDimensionに使用されます。 cs-uri-query(bb)は空ではなく、cs-uri-query(a)が「2」の処理モードIDと一致すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは、クライアント側のディメンション処理モードで、わかりやすい値で再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> cs-uri-query(ba)値は、このシンプルDimensionに使用され、Pingレベルで構築されます。 このディメンションは、現在監視中のプロファイルの名前を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック秒</b> </td> 
   <td colname="col2"> この数値Dimensionにはcs-uri-query(h)値が使用されます。 cs-uri-query(a)が「1」に一致するという条件がPingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェックの成功</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-query(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Real Time Processing Percentage</b> </td> 
   <td colname="col2"> Pingレベルで作成されたcs-uri-query(t)値を使用する数値Dimension。 cs-uri-query(a)は「1」に一致するように条件付けされます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も後ろのソース</b> </td> 
   <td colname="col2"> Pingレベルで構築されたcs-uri-query(bl)値から構築されたシンプルなDimension。 このディメンションは、データソースとの最後の連絡が発生した日時を表示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2">cs-uri-query(an)値を使用して構築された数値Dimension。Pingレベルで構築されます。 cs-uri-query(k)は空ではなく、cs-uri-query(a)は「1」に一致するように条件付けされます。 特定のサーバー上のTemp DB領域の使用率を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2">cs-uri-query(bf)値は、この数値ディメンションに使用されます。 Pingレベルで構築されます。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchのバージョン</b> </td> 
   <td colname="col2"> このシンプルなDimensionには、cs-uri-query(ab)値が使用されます。 これはPingレベルで構築され、cs-uri-query(ab)が空でなく、cs-uri-query(a)が「1」に一致する条件が設定されます。 各サーバーで実行されているData Workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchのバージョン（メジャー）</b> </td> 
   <td colname="col2"> cs-uri-query(ab)の値が分割され、メジャーリリース値がx-insight-version-majorフィールドにコピーされます。 これは、Pingレベルで構築され、x-insight-version-majorが空でなく、cs-uri-query(a)が「1」に一致する条件が設定されたシンプルなDimensionです。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
