---
description: 次のディメンションは、Data Workbenchの履歴プロファイルで使用できます。
title: Data Workbench 履歴プロファイルのディメンション
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
translation-type: tm+mt
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
   <td colname="col2">この設定で可算となるのはこのみで、すべてのディメンションのルートです。 ブロックはサーバーと見なすことができます。 x-trackingidフィールドを使用しています。 <p>注意： ブロックIDは、サーバ名とホスト名のハッシュです。したがって、プロファイルごとに約1ブロックあります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> これは、Block可算から作成された可算ディメンションです。 プロファイル内の各データ行は、監視エージェントからのpingです。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告 — 重要</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ad)値から作成された数値Dimension。 cs-uri-クエリ(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>アラートダウン</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ac)値から作成された数値Dimension。 これはPingレベルで構築され、cs-uri-クエリ(a)が"1"に一致すると条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警告</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ae)値から作成された数値Dimension。 cs-uri-クエリ(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイルの再処理</b> </td> 
   <td colname="col2"> cs-uri-クエリ(aa)値から作成された数値Dimension。 cs-uri-クエリ(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>遅延時間（分）の基準</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bi)は、x-as-of-delay-minutesフィールドに配置され、最も近い分に丸められます。 cs-uri-クエリ(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>生産能力行の割合</b> </td> 
   <td colname="col2"> cs-uri-クエリ(r)値から作成された数値Dimension。 cs-uri-クエリ(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量サイズの割合</b> </td> 
   <td colname="col2"> cs-uri-クエリ(n)値から作成された数値Dimension。 cs-uri-クエリ(a)が"1"に一致し、cs-uriquery(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>コンポーネントチェックの成功</b> </td> 
   <td colname="col2"> cs-uri-クエリ(v)値から構築された単純なDimension。 これはPingレベルで構築され、cs-uri-クエリ(a)が"1"に一致すると条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>エラーのあるコンポーネント</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ao)は、区切り文字「|」で分割され、x-components-in-errorフィールドにコピーされます。 x-components-in-errorフィールドから作成された多対多Dimension。 Pingレベルで構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェック秒数</b> </td> 
   <td colname="col2"> cs-uri-クエリ(l)値から作成された数値Dimension。 cs-uri-クエリ(k)が空でないというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細チェックの成功</b> </td> 
   <td colname="col2"> cs-uri-クエリ(k)値から構築された単純なDimension。 cs-uri-クエリ(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bc)がx-dimension-gagobiteフィールドにコピーされます。 x-dimension-gagobitsフィールドは、このシンプルDimensionのユーザーで、「2」との一致に対するcs-uri-クエリ(a)に基づいています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ディスク「x」の使用率</b> </td> 
   <td colname="col2"> これらの数値Dimensionは、cs-uri-クエリ(ah、ai、aj、ak、al)値から設定されます。 これらはPingレベルで構築され、cs-uri-クエリ(a)が"1"に一致し、cs-uri-クエリ(k)が空ではないことに基づいて条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>推定スイープデカス秒</b> </td> 
   <td colname="col2"> この数値Dimensionでは、x-estimated-sweep-decasecondsフィールドが使用されます。 これは、サーバの推定スイープ時間を10で割った値です（寸法をより適正なサイズにするために、スイープ測定の解像度を低くした値）。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Input MegaBytes/Minute</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(bj)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Inputに含まれている場合、この数値Dimensionの値には、システムがデータを入力する1分あたりのMBが表示されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Fast Merge MegaBytes/Minute</b> </td> 
   <td colname="col2">この寸法には、cs-uri-クエリ(bk)値が使用されます。 ブロックの最後の行は、ディメンションの値として使用されます。 データセットがFast Mergeに設定されている場合、この数値Dimensionの値には、システムがマージされる1分あたりのMB数が表示されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Field GigaBytes</b> </td> 
   <td colname="col2">このディメンションには、cs-uri-クエリ(bg)値が使用されます。 値を1000で割り、最も近い整数に丸めます。 この数値Dimensionの値は、データセット内のフィールドで使用されている領域のサイズを表示します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>グループ</b> </td> 
   <td colname="col2"> cs-uri-クエリ(x)値からPingレベルで構築された単純なDimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ホスト</b> </td> 
   <td colname="col2"> このディメンションには、cs-uri-クエリ(b)値が使用されます。 シンプルディメンションの値は、ブロックの最後の行です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最後のPing</b> </td> 
   <td colname="col2"> x-unixtimeフィールドはx-last-pingにコピーされ、10で割ってカーディナリティが減少します。 数値Dimensionはブロックレベルで構築され、x-last-pingフィールドを使用します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>負荷平均</b> </td> 
   <td colname="col2"> これは、指定したサーバーのcs-uri-クエリ(i)値に対して、Last Rowを使用する数値ディメンションです。 cs-uri-クエリ(k)が空でないことが条件となります。 このディメンションは、監視対象システム内のサーバーの平均負荷の計算に使用されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Log Reading Percentage</b> </td> 
   <td colname="col2">cs-uri-クエリ(be)値は、Pingレベルで構築されたこの数値ディメンションに使用されます。 このディメンションは、読み取られるログの割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリページファイルの割合</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-クエリ(o)値を使用するNumericディメンションです。 これは、cs-uri-クエリ(k)が空でないことと、cs-uri-クエリ(a)が"1"に一致することに条件が当てられます。 このディメンションは、ページファイルのメモリ使用量の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリ物理メガバイト合計</b> </td> 
   <td colname="col2">これは、Pingレベルで構築されたcs-uri-クエリ(ag)値を使用するNumericディメンションです。 これは、cs-uri-クエリ(k)が空でないことと、cs-uri-クエリ(a)が"1"に一致することに条件が当てられます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリの物理的割合</b> </td> 
   <td colname="col2">これは、Pingレベルで構築されたcs-uri-クエリ(ag)値を使用するNumericディメンションです。 これは、cs-uri-クエリ(k)が空でないことと、cs-uri-クエリ(a)が"1"に一致することに条件が当てられます。 このディメンションは、各サーバーの物理メモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>メモリクエリの割合</b> </td> 
   <td colname="col2"> これは、Pingレベルでcs-uri-クエリ値を使用するNumericディメンションです。 cs-uri-クエリ(k)が空でないことと、cs-uri-クエリ(a)が"1"に一致することが条件となります。 このディメンションは、各サーバーのクエリメモリ使用率の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ネットワーク接続</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-クエリ(q)値を使用するNumericディメンションです。 cs-uri-クエリ(k)が空でないことと、cs-uri-クエリ(a)が"1"に一致することが条件となります。 これは、特定のサーバーのネットワーク接続数を示すために使用します。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出力行</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bh)値を100000で割り、x-output-rowsフィールドにコピーして、ディメンションのサイズを小さくします。 X-output-rowsは、Pingレベルで構築されたNumericDimensionで使用され、cs-uri-クエリ(a)が"2"に一致するという条件が付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>PingタイプID</b> </td> 
   <td colname="col2"> cs-uri-クエリ(a)値をPingレベルで使用して構築された単純なDimension。 これは、どのようなPingが記録されたかを示します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ポーリング待ち時間（センチ秒）</b> </td> 
   <td colname="col2">cs-uri-クエリ(m)の値を10で割ってディメンションサイズを小さくし、x-poll-latency-centicedsフィールドにコピーします。 これは、Pingレベルで構築されたNumericディメンションで、cs-uri-クエリ(k)が空ではなく、cs-uri-クエリ(a)が「1」/に一致するという条件が付けられます。このディメンションは、ポーリング待ち時間の計算に使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>処理モードID</b> </td> 
   <td colname="col2"> cs-uri-クエリ(bb)値は、Pingレベルで構築されたこのシンプルDimensionに使用されます。 cs-uri-クエリ(bb)は空ではなく、cs-uri-クエリ(a)が「2」の処理モードIDに一致すると、システムの処理モード(Fast Input、Fast Merge、Real Time)を確認できます。 <p>注意： このディメンションは、非表示になった後、クライアント側のディメンション処理モードでフレンドリ値を使用して再公開されます。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>プロファイル</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ba)値は、このシンプルDimensionに使用され、Pingレベルで構築されます。 このディメンションには、現在監視中のプロファイルの名前が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック秒数</b> </td> 
   <td colname="col2"> このNumericDimensionには、cs-uri-クエリ(h)値が使用されます。 cs-uri-クエリ(a)が"1"に一致するというPingレベルの条件で構築されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>クイックチェック成功</b> </td> 
   <td colname="col2"> これは、Pingレベルで構築されたcs-uri-クエリ(g)値から構築されたシンプルディメンションです。 クイックチェック指標の計算に使用されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>リアルタイム処理の割合</b> </td> 
   <td colname="col2"> Pingレベルで構築されたcs-uri-クエリ(t)値を使用する数値Dimension。 cs-uri-クエリ(a)が「1」に一致することを条件付けられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最も後のソース</b> </td> 
   <td colname="col2"> Pingレベルで構築されたcs-uri-クエリ(bl)値から構築された単純なDimension。 このディメンションには、データソースとの最後の接触が発生した日時が表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>一時DB領域の割合</b> </td> 
   <td colname="col2">cs-uri-クエリ(an)値を使用して構築された、Pingレベルで構築された数値Dimension。 cs-uri-クエリ(k)は空ではなく、cs-uri-クエリ(a)は「1」に一致すると条件付けられます。 特定のサーバー上で使用されている一時DB領域の割合を計算するために使用されます。 <p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>変換の割合</b> </td> 
   <td colname="col2">この数値ディメンションには、cs-uri-クエリ(bf)値が使用されます。 これはPingレベルで構築されます。 このディメンションは、完全なデータ変換の割合を計算するために使用されます。 <p><p>注意： このディメンションは、指標に平均化される場合にのみ役立つので、非表示になります。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchバージョン</b> </td> 
   <td colname="col2"> この単純なDimensionには、cs-uri-クエリ(ab)値が使用されます。 これはPingレベルで構築され、cs-uri-クエリ(ab)が空ではなく、cs-uri-クエリ(a)が「1」に一致することが条件付きです。 これにより、各サーバーで実行されているdata workbenchサーバーのバージョンが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbenchバージョンメジャー</b> </td> 
   <td colname="col2"> cs-uri-クエリ(ab)値が分割され、メジャーリリース値がx-insight-version-majorフィールドにコピーされます。 これは、Pingレベルで構築された単純なDimensionで、x-insight-version-majorが空でないこと、およびcs-uri-クエリ(a)が"1"に一致することを条件付けられています。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
