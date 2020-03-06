---
description: Data Workbenchには、組み込みディメンションが含まれています。
solution: Analytics
title: 組み込みディメンション
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 組み込みディメンション{#built-in-dimensions}

Data Workbenchには、組み込みディメンションが含まれています。

次の表に、Data Workbenchで使用できる組み込みディメンションを示します。

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名前 </th> 
   <th colname="col2" class="entry"> 詳細 </th> 
   <th colname="col3" class="entry"> レベル </th> 
   <th colname="col4" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> なし </td> 
   <td colname="col2"> 派生 </td> 
   <td colname="col3"> 該当なし </td> 
   <td colname="col4">すべてのディメンションのすべての要素に関連する単一の要素「」を持ちます。 指標を「なし」で評価するのは、ディメンションなしで評価するのと似ています。 <p>[ <span class="filepath"> None=""]フィルタは</span> 、[True]と <span class="filepath"> 同じです</span>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1（非表示） </td> 
   <td colname="col2"> 数値 </td> 
   <td colname="col3"> 該当なし </td> 
   <td colname="col4">要素「1」は、同じく序数値 <span class="filepath"> = 1で、すべてのディメンションのすべての</span>要素に関連しています。 通常、Oneディメンションは、次の構文を使用してカウントを作成するために使用されます。 <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

