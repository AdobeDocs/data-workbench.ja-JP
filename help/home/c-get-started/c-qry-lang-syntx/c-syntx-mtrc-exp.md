---
description: 指標は、指標エディターを使用して編集し、プロファイルの Metrics ディレクトリに保存できます。
solution: Analytics
title: 指標式の構文
topic: Data workbench
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Syntax for metric expressions{#syntax-for-metric-expressions}

指標は、指標エディターを使用して編集し、プロファイルの Metrics ディレクトリに保存できます。

詳しくは、「派生指標の作成 [と編集」を参照してください](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)。 指標式はワークシートで使用することもできます。詳しくは、「 [ワークシート](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). 指標式を定義するには、次の構文を使用します。

メモ:

1. 下線を引いた語句は、式のテキストにそのまま入力する必要があります。
1. {TEXT}? の形式は、オプションのテキストを表します。
1. {TEXT}* の形式は、0 回以上発生するテキストを表します。
1. {A | B | C |...} の形式は、A または B または C... のように、所定のオプションのうちの 1 つのみから成るテキストを表します。
1. [A,B) の形式は、A 以上 B 未満の数値の範囲を表します。

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別子 </p> </td> 
   <td colname="col2"> <p>識別子は、名前付き指標を参照するものです。正しい識別子のルールについては、「<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">識別子の構文</a>」を参照してください。 </p> <p>例：Revenue = Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(指標) </p> </td> 
   <td colname="col2"> <p>(指標) という式の結果は、指標の式の結果と同じです。丸括弧は、式の中の演算の順序を指定します。 </p> <p>例：Average = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果の和。 </p> <p>例：Value = Revenue + Cost_Savings </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果の差。 </p> <p>例：利益=売上高 — コスト </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果の積。 </p> <p>例：Dollars = Cents * 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A / B </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果の比。 </p> <p>例：Revenue_per_Session = Revenue / Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>指標 A の結果を指標 B の結果でべき乗した値。 </p> <p>例：Area = Width^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric) </p> </td> 
   <td colname="col2"> <p>指標の標準偏差の推定値。これは、ジャックナイフ法として知られている標本化技術を使用して計算されます。 </p> <p>この指標はメモリを大量に使用するので、大きなテーブルには使用できません。 </p> <p>この構文を使用するには、適切なプロパティのジャックナイフディメンション（名前は「jackknife」）が存在する必要があります。詳しくは、Adobe Consulting Services にお問い合わせください。 </p> <p>例：confidence(Average_Score) </p> <p> <p>注意：confidence(metric) や confidence(metric,jacknife) などの信頼性指標タイプは、特に Adobe の対照実験機能を使用する場合に役立ちます。対照実験中に指標が 12 ％から 16 ％に急上昇した場合、信頼性引き出し線を使用して、その上昇がランダムな変化による確率を計算できます。これにより、限られた証拠から誤った結論を導き出さないようにできます。逆に言えば、疑わしい変化が実は本当であるという保証も提供できます。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confidence(metric, jackknife) </p> </td> 
   <td colname="col2"> <p>指標の標準偏差の推定値。これは、ジャックナイフ法として知られている標本化技術を使用して計算されます。この構文では、名前が「jackknife」以外のジャックナイフディメンションを使用して、指標の信頼性を決定できます。 </p> <p>この指標はメモリを大量に使用するので、大きなテーブルには使用できません。 </p> <p>この構文を使用するには、適切なプロパティのジャックナイフディメンション（名前は「jackknife」以外）が存在する必要があります。詳しくは、Adobe Consulting Services にお問い合わせください。 </p> <p>例：confidence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>参照しているセルの内容を指標式として扱います。この構文は、ワークシートのビジュアライゼーションにおいてのみ使用できます。 </p> <p>例：eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>数学的な対数関数。指標 X はパラメーターで、指標 B が底です。 </p> <p>例：dB = 20*log(Amplitude,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric[Filter] </p> </td> 
   <td colname="col2"> <p>「Filter をかけた Metric」。つまり、指定したフィルターによってフィルタリングされた新しい指標です。 </p> <p>例：Jan_Sessions = Sessions[ Month=”Jan” ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Metric by Dimension </p> </td> 
   <td colname="col2"> <p>ディメンションの「レベル」で評価した指標。(M by X)[F] の結果（指標「M by X」をフィルター「F」で評価した結果）は、M[F by X] （指標「M」をフィルター「F by X」で評価した結果）です。 </p> <p>例：AB_Visitors = </p> <p>(Visitors by Session)[Page=”A” and Page=”B”] = </p> <p>Visitors[(Page=”A” and Page=”B”) by Session] = </p> <p>同じセッションでページ A とページ B を訪問した訪問者数 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数値 </p> </td> 
   <td colname="col2"> <p>固定値の指標。 </p> <p>例：Pi = 3.1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>指標の評価対象のディメンションをすべて無視します。そのディメンションのすべての要素に対して、指標は同じ値になります。 </p> <p>例：Pct_of_Visitors = Visitors / total(Visitors) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Metric) </p> </td> 
   <td colname="col2"> <p>指標に適用するフィルターを無視します。指標は、選択などのフィルターの影響を受けません。 </p> <p>例：Benchmark_Sessions = all( Sessions ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(Metric)) </p> </td> 
   <td colname="col2"> <p>すべてのフィルターとディメンションを無視します。適用されるフィルターやディメンションにかかわらず、指定したプロファイル全体で値は同じになります。 </p> <p>例：Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Visitor、Session などの可算ディメンションをカウントする指標。 </p> <p>例：Visitors = sum(One,Visitor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>ある可算ディメンションに関して数値ディメンションを合計する指標。数値ディメンションの要素である順序の値（書式設定された値ではない）が使用されるので、ほとんどの場合、結果に倍率を適用する必要があります。 </p> <p>例：Value = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果のうち小さい方。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>指標 A と指標 B の結果のうち大きい方。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>指標 A と同一の指標ですが、指標 B の書式設定機能を使用します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

