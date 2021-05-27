---
description: 数値ディメンションは、順序付け可能な数値エレメントで構成され、その親の可算ディメンションとの間に 1 対多の関係を持ちます。
title: 数値ディメンション
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 97%

---

# 数値ディメンション{#numeric-dimensions}

数値ディメンションは、順序付け可能な数値エレメントで構成され、その親の可算ディメンションとの間に 1 対多の関係を持ちます。

数値ディメンションは、親ディメンションのエレメントが持つ数値プロパティを表したもの、と考えることができます。例えば、Web データを扱っている場合、Session ディメンションを切り口として各セッションの売上金額（ドル単位）を定義する Session Revenue（セッション売上）という数値ディメンションを定義することができます。セッションごとの売上は 1 つだけですが、売上金額が同じであるセッションは複数存在する可能性もあります。したがって、Session Revenue ディメンションと Session ディメンションには 1 対多の関係が存在することになります。

数値ディメンションは多くの場合、値を合計したり、特定の条件の出現回数をカウントしたり、最小／最大値を特定したりするための指標を定義するときに使用します。例えば、Revenue（売上）という指標は、Session Revenue（セッション売上）ディメンションを使用して sum(Session_Revenue, Session) と定義することができます。このように、Revenue 指標を定義することによって、選択されたセッションの総売上高を得ることができます。

数値ディメンションを他のディメンションの親にすることはできません。

数値ディメンションは、以下のパラメーターによって定義します。

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col2"> Data Workbench に表示される、ディメンションのわかりやすい名前。ディメンション名にハイフン（-）を含めることはできません。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clip Values </td> 
   <td colname="col2"> true または false。Min 値と Max 値の範囲に収まるように（演算後の）入力値をクリッピングするかどうかを指定します。Clip Values が true の場合、指定された範囲に値がクリッピングされます。Clip Values が false の場合、親ディメンションのエレメントの値は返されません。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）拡張ディメンションについてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 入力フィールドが数値ディメンションの作成に寄与する条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fixed Size </td> 
   <td colname="col2"> true または false。ディメンション内のエレメント数（ユニーク数）を制御します。true の場合、Min と Max の範囲のすべてのエレメントがディメンションに含められます。false の場合、値が追加されるにつれてディメンションのサイズが大きくなります。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden </td> 
   <td colname="col2"> Data Workbench のインターフェイスにディメンションを表示するかどうかを指定します。デフォルトでは false に設定されています。例えば、指標の基準としてのみ使用されるディメンションであれば、このパラメーターを true に設定して、Data Workbench に表示されないようにすることができます。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> <p>指定した演算に使用する値または出現回数のカウント対象となる入力値。 </p> <p> このフィールドが文字列ベクトルである場合、ベクトルに含まれるエレメントごとに評価が実行されます。例えば、ベクトルの長さが 3 で、Operation が COUNT である場合、カウントに 3 が加算されます。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> 最終的に得られるディメンションの下限。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> 最終的に得られるディメンションの上限。 </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Offset </td> 
   <td colname="col2"> この表の「Scale」を参照してください。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>利用可能な演算は次のとおりです。 </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> COUNT：全ログエントリ中、ディメンションの Condition を満たす <span class="wintitle">Input</span> フィールドの、ブランクではない値の総数が使用されます。<span class="wintitle">Input</span> フィールドがベクトルフィールドである場合、各ログエントリの、ブランクではない値の総数がカウントされます。 </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> FIRST NONBLANK：ブランクではない最初の入力値が使用されます。最初のログエントリからの入力値であるとは限りません。<span class="wintitle">Input</span> がベクトルフィールドである場合、関連するログエントリのベクトルの先頭行が使用されます。その値が数値ではない場合、いずれの値も使用されません。 </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> FIRST ROW：入力がブランクであった場合も含め、親ディメンションエレメントに関連した最初のログエントリの値が使用されます。<span class="wintitle">Input</span> がベクトルフィールドである場合、関連するログエントリのベクトルの先頭行が使用されます。その値がブランクであるか、数値以外であった場合、あるいは、関連するログエントリがディメンションの Condition を満たしていない場合は、いずれの値も使用されません。 </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> LAST NONBLANK：ブランクではない最後の入力値が使用されます。最後のログエントリからの入力値であるとは限りません。<span class="wintitle">Input</span> がベクトルフィールドである場合、関連するログエントリのベクトルの先頭行が使用されます。その値が数値ではない場合、いずれの値も使用されません。 </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> LAST ROW：入力がブランクであった場合も含め、親ディメンションエレメントに関連した最後のログエントリの値が使用されます。<span class="wintitle">Input</span> がベクトルフィールドである場合、関連するログエントリのベクトルの先頭行が使用されます。その値がブランクであるか、数値以外であった場合、あるいは、関連するログエントリがディメンションの Condition を満たしていない場合は、いずれの値も使用されません。 </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUM：全ログエントリ中、ディメンションの Condition を満たす <span class="wintitle">Input</span> フィールドのすべての数値の合計が使用されます。該当するログエントリが存在しない場合や、数値が見つからない場合、0（数値）が使用されます。 </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN または MAX：全ログエントリ中、ディメンションの Condition を満たす <span class="wintitle">Input</span> フィールドの最小または最大の数値。該当するログエントリが存在しない場合や、数値が見つからない場合、いずれの値も使用されません。 </li> 
     </ul> </p> <p> <p>注意：意図したディメンションが確実に定義されるように演算を指定する必要があります。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> 親ディメンションの名前。すべての可算ディメンションは、親ディメンションになることができます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> <p>ディメンションの序数値を得るために、Operation の結果が次のように変換されます。 </p> <p> (Scale * Input) + Offset </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL Operation]で値が得られない場合、または[!DNL Clip Values]がfalseで、値が[!DNL Min]と[!DNL Max]の間でない場合、数値ディメンションの要素は親ディメンションの要素に関連付けられません。

次の例は、Web サイトトラフィックから収集されたイベントデータを使用する数値ディメンションの定義です。この数値ディメンション（Ad View Counter）は、特定のセッション期間中に訪問者が広告を閲覧した回数をカウントします。Web サーバーからの広告リソース要求がすべて、「ad=」を含んだ cs-uri-query で行われることを前提としています。この例で関心の対象となっているのは、フィールドの実際の値ではなく、訪問者に広告が表示された回数（COUNT）です。

![](assets/cfg_Transformation_Dim_Numeric.png)
