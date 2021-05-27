---
description: Data Workbenchには、組み込みのディメンションが含まれています。
title: 組み込みディメンション
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 15%

---

# 組み込みディメンション{#built-in-dimensions}

Data Workbenchには、組み込みのディメンションが含まれています。

次の表に、Data Workbenchで使用可能な組み込みディメンションを示します。

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
   <td colname="col4">すべてのディメンションのすべての要素に関連する単一の要素「」を持つ。 「なし」に対する指標の評価は、ディメンションなしに対する指標の評価と似ています。 <p><span class="filepath">フィルター[なし=""]</span>は、<span class="filepath"> [True]</span>と同じです。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1つ（非表示） </td> 
   <td colname="col2"> 数値 </td> 
   <td colname="col3"> 該当なし </td> 
   <td colname="col4">要素「1」（序数値<span class="filepath"> = 1</span>も含む）は、すべてのディメンションのすべての要素に関連します。 通常、「1」ディメンションは、次の構文を使用してカウントを構成するために使用します。 <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
