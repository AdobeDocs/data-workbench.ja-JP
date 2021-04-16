---
description: CrossRows 変換は、他の変換と同様、ログソース内のデータ行（ログエントリ）に対して適用されます。
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 98%

---

# CrossRows{#crossrows}

CrossRows 変換は、他の変換と同様、ログソース内のデータ行（ログエントリ）に対して適用されます。

個々のデータ行について、指定した入力フィールドの値が変換処理に渡され、一連の処理ステップが実行されて、指定した出力フィールドに結果が記録されます。ただし、[!DNL CrossRows] 変換では、その処理対象が、ある特定のデータ行（この行を出力行と呼びます）であるとき、その行に加え、同じ追跡 ID に関連付けられている 1 つまたは複数のデータ行（これらの行を入力行と呼びます）が考慮されます。したがって、特定の追跡 ID に関して、各出力行の出力フィールドの値は、1 つまたは複数の入力行の入力フィールドの値によって決まります。

この変換には、入力行を制限するための様々な条件や制約が用意されています。これらの制限は、Data Workbench サーバーの各種条件（[条件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)を参照）、出力行を基準とした入力行の範囲、出力行の時刻を基準とした時間の範囲の観点で指定することができます。その変換の条件と制約を満たした入力行を対象に演算（SUM など）を適用し、出力フィールドの値を求めることができます。

>[!NOTE]
>
>[!DNL CrossRows] 変換が正しく動作するためには、ソースデータにおいて、データが時系列順に並んでおり、追跡 ID ごとにグループ化されている必要があります。したがって、[!DNL CrossRows]は[!DNL Transformation.cfg]ファイルまたは[!DNL Transformation Dataset Include]ファイルで定義されている場合にのみ機能します。

以降、次の点を踏まえて、表内のパラメーターの説明をお読みください。

* 出力行とは、ある特定の時点における変換の処理対象となるデータ行です。
* 入力行とは、その他すべてのデータ行です（出力行の前後の行や、出力行そのものを含む）。入力行の入力フィールドの値が変換の入力として使用されます。入力行には、Input Condition、Key、Row Begin、Row End、Time Begin、Time End の各パラメーターが適用されます。

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> 変換のわかりやすい名前。ここには任意の名前を入力することができます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）変換についてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 変換の出力を特定のログエントリに限定します。特定のログエントリがその条件を満たしていない場合、Output パラメーターのフィールドは変更されません。ただし、その入力内容が引き続き使用され、他のログエントリに影響を及ぼす可能性はあります。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> 入力行のフィールドのうち、入力として使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Condition </td> 
   <td colname="col2"> 特定の入力行からのみ変換の入力を受け入れます。特定の入力行が Input Condition を満たしていない場合、その行の入力フィールドは無視され、他の出力行に影響を与えません。ただし、その行の出力フィールドには、指定された条件に従って変更が加えられます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> キー </td> 
   <td colname="col2"> <p>（オプション）キーとして使用するフィールドの名前。 </p> <p> キーを指定した場合、特定の出力行に使用される入力行が、出力行と同じ Key 値を持つ連続する行ブロックに限定されます。この制限は、<span class="wintitle">CrossRows</span> 変換に対する他のパラメーターによって入力行に設定されたすべての制限に加えて適用されます。 </p> <p> 例えば、Web データを扱っているとき、x-session-key フィールド（セッションごとの一意の値）をキーとした場合、変換の対象となる入力行は、出力行と同じ x-session-key 値を持つ行に限定されます。そのため、考慮されるのは、出力行と同じセッション期間に生じたページビューを表す入力行のみとなります。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>それぞれの出力行について特定の出力を得るために、Input Condition、Key、Row Begin、Row End、Time Begin、Time End の各パラメーターで定義された全条件を満たしたすべての入力行に適用される演算。 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL：入力行からそのフィールドのすべての値を受け取って、それらをベクトルとして出力します。 </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM：入力行のフィールドの値を数値として解釈し、それらを合計します。 </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> FIRST ROW：先頭の入力行の入力フィールドの値を出力します。 </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW：最後の入力行の入力フィールドの値を出力します。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> 出力フィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Row Begin／Row End </td> 
   <td colname="col2"> <p>（オプション）出力行を基準として入力行の範囲を指定します。例えば、Row Begin の値が「0」である場合、出力行より前にあるすべての行が除外されます。Row Begin の値が「1」である場合、その出力行も除外されます。代表的な範囲の例を次に示します。 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> Begin 0：基準となる行とそのすべての後続行 </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> Begin 1：すべての後続行 </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> End 0：基準となる行とそのすべての先行行 </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> End -1：すべての先行行 </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> Begin -1、End -1：前の行 </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> Begin 1、End 1：次の行 </li> 
     </ul> </p> </td> 
   <td colname="col3"> すべての行 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Begin／Time End </td> 
   <td colname="col2"> <p>（オプション）出力行の時刻を基準として時間の範囲を指定します。例えば、Time End を 30 分とした場合、出力行の発生後 30 分以内に生じたすべての行が対象となります。Time Begin を -30 分とした場合、出力行の発生前 30 分以内に生じたすべての行が対象となります。 </p> <p> 日、週、時間、分、ミリ秒（ms）、ティック（100 ns）、ナノ秒（ns）の各時間単位を利用できます。 </p> </td> 
   <td colname="col3"> 全時間 </td> 
  </tr> 
 </tbody> 
</table>

次の例では、Web データの行に [!DNL CrossRows] 変換を適用し、ページビューごとに、次回のページビューの時刻を調べています。既に述べたように、[!DNL CrossRows] はデータセット構築プロセスの変換段階でのみ適用されます。そのためデータ行は、訪問者別（各訪問者には一意の追跡 ID が割り当てられています）および時系列順に並べ替えられます。

入力フィールドである x-timestamp は、x-is-page-view フィールドに値が格納されている入力行（つまりページビューを表すデータ行）についてのみ考慮されます。Key パラメーターには x-session-key フィールド（セッションごとに一意の値を持ちます）が指定されています。そのため、変換の入力行（ログエントリ）は、出力行と同じ x-session-key 値を持つ連続する行ブロックに限定されます。つまり、ある特定の入力行が変換の対象となるためには、出力行のページビューと同じセッション期間に生じたページビューを表している必要があります。first row 演算は、[!DNL Input] Condition を満たし、なおかつ出力行と同じ x-session-key 値を持つ先頭の入力行から、出力フィールドの値を生成します。

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] の実行時間は、その入力と出力を足したサイズに比例します。つまり、SUM、FIRST ROW、LAST ROW の各演算に限って言えば、効率は他の変換と同程度となります。一方、ALL については、事情がもっと複雑です。なぜなら、[!DNL CrossRows] の設定によっては、特定の追跡 ID に該当する行（ログエントリ）の総数に比例した量のデータが、すべてのデータ行（ログエントリ）について出力されるためです。
