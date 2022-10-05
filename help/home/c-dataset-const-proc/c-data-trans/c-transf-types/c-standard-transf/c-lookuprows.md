---
description: LookupRows 変換は、同じ追跡 ID を持った他のログエントリを調べ、出力フィールドの値を、入力行に指定されたフィールドの値に設定します。
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 92%

---

# LookupRows{#lookuprows}

{{eol}}

LookupRows 変換は、同じ追跡 ID を持った他のログエントリを調べ、出力フィールドの値を、入力行に指定されたフィールドの値に設定します。

調べる対象がルックアップファイルではなくログエントリであるという点で、[!DNL LookupRows] 変換は [!DNL CrossRows] 変換とよく似ています。詳しくは、 [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

[!DNL LookupRows] 変換が正しく動作するためには、ソースデータにおいて、データが時系列順に並んでおり、追跡 ID ごとにグループ化されている必要があります。したがって [!DNL LookupRows] は、 [!DNL Transformation.cfg] ファイル内または [!DNL Transformation Dataset Include] ファイル。

以降、次の点を踏まえて、表内のパラメーターの説明をお読みください。

* 出力行とは、ある特定の時点における変換の処理対象となるデータ行です。
* 入力行とは、その他すべてのデータ行です（出力行の前後の行や、出力行そのものを含む）。入力行の入力フィールドの値が変換の入力として使用されます。

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> （オプション）。変換についてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 変換の出力を特定のログエントリに限定します。特定のログエントリがその条件を満たしていない場合、Output Row Value Output パラメーターのフィールドは変更されません。ただし、その入力内容が引き続き使用され、他のログエントリに影響を及ぼす可能性はあります。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Condition </td> 
   <td colname="col2">特定の入力行からのみ変換の入力を受け入れます。特定の入力行が <span class="wintitle">Input</span> Condition を満たしていない場合、その行の入力フィールドは無視され、他の出力行に影響を与えません。ただし、その行の出力フィールドには、指定された条件に従って変更が加えられます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Row Key Input </td> 
   <td colname="col2"> 入力行のキーとして使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Row Value Input </td> 
   <td colname="col2"> すべての条件が満たされ、Output Row Value Output パラメーターのフィールドに値がコピーされるとき、そのコピー元となる入力行のフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>それぞれの出力行について特定の出力を得るために、<span class="wintitle">Input</span> Condition パラメーターと Input Row Key Input パラメーターで定義された全条件を満たしたすべての入力行に適用される演算。 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST は、（出力行より後ろの最初に一致した行ではなく）データ内で最初に一致した入力行から、Input Row Value Input パラメーターで指定されたフィールドの値を出力します。 </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST は、（出力行より前の最後に一致した行ではなく）データ内の最後の入力行から、Input Row Value Input パラメーターで指定されたフィールドの値を出力します。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Row Key Input </td> 
   <td colname="col2"> 出力行のキーとして使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Row Value Output </td> 
   <td colname="col2">すべての条件が満たされ、Input Row Value Input パラメーターのフィールドから値がコピーされるとき、そのコピー先となる出力行のフィールドの名前。同じ x-trackingid 値と <span class="wintitle">Output Row Key Input </span> 値を持つ出力行はすべて、同じ <span class="wintitle">Output Row Value Output</span> の値を持ちます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Input Row Key Input、Input Row Value Input、Input Condition のすべてのパラメーターが組み合わさって、追跡 ID ごとのルックアップファイルが定義されるのに対し、Output Row Key Input、Output Row Value Input、Condition の各パラメーターは、ファイル内のルックアップの対象と、Output Row Value Output によって指定されたフィールドに格納される値を定義します。

この変換の動作について理解を深めるために押さえておくべき要点を以下にまとめました。

* Condition を満たしており、なおかつ Output Row Key Input が空以外である各出力行について、次の処理が実行されます。

   * 次の条件をすべて満たした先頭（FIRST）または最後（LAST）の入力行を探します。

      * 入力行が Input Condition を満たしている。
      * 入力行の x-trackingid が出力行の x-trackingid と等しい。
      * 入力行の Input Row Key Input が出力行の Output Row Key Input と等しい。

* そのうえで、出力行の Output Row Value Output を入力行の Input Row Value Input に設定します。

の考慮事項 [!DNL LookupRows]

* ブランクのキー値は、どのような値とも一致しません。空白のキーと、 [!DNL Input Condition]、 [!DNL Output Row Key Input] の「」が常に [!DNL Output Row Value Output] 」の

* で禁止されていない場合 [!DNL Input Condition]を指定した場合、行は自分で検索することができます [!DNL Input Row Key Input] および [!DNL Output Row Key Input] 値が同じである。

複数のキー値がある場合、 [!DNL Format] 変換 ( [形式](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) をクリックしてから [!DNL LookupRows] 変換。

ペットの登録ページを設けた Web サイトがあるとします。登録ページで名前と品種を入力すると、後から、そのペットの名前に特化した「おもちゃの購入」ページが表示されます。この場合、登録ページに入力されたペットの品種に対してペットの名前をリンクさせるしくみが必要です。そのためには、次のような [!DNL LookupRows] 変換を作成することが考えられます。

![](assets/cfg_TransformationType_LookupRows.png)

この例を先ほどの要点と照らして考えてみましょう。

* 条件を満たしており、なおかつ cs-uri-query(petname) の値が空以外である各出力行について、次の処理が実行されます。

   * 次の条件をすべて満たした最後（LAST）の入力行を探します。

      * 入力行に、空以外の cs-uri-query(petbreed) 値を含む。
      * 入力行の x-trackingid が出力行の x-trackingid と等しい。
      * 入力行の cs-uri-query(petname) の値が、出力行の cs-uri-query(petname) の値と等しい。

* 出力行の x-pet-breed の値を入力行の cs-uri-query(petbreed) の値に設定します。

この [!DNL LookupRows] 変換では、ペットの名前（キー）を使用して、ペットの登録ページとおもちゃの購入ページの両方にペットの品種が確実に関連付けられるので、複数のペットを飼っている訪問者であっても、ペットの品種ごとに購入されたおもちゃを分析することができます。
