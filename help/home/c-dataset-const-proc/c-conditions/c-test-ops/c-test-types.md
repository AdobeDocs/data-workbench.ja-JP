---
description: Compare 条件と Range 条件では、使用する比較のタイプを指定する必要があります。
title: テスト演算のタイプ
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 96%

---

# テスト演算のタイプ{#test-types-for-test-operations}

{{eol}}

Compare 条件と Range 条件では、使用する比較のタイプを指定する必要があります。

次の表に、使用可能なタイプ ( [!DNL LEXICAL], [!DNL NUMERIC]、および [!DNL DATETIME]) をクリックします。

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> テストの種類 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> メモ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>最初に、入力フィールドが整数に変換されます。変換できない場合は、0（ゼロ）が値として使用されます。入力値から得られる整数が、指定した最小値以上、最大値以下である場合にのみ、true が返されます。 </p> </td> 
   <td colname="col3"> <p>最小フィールドまたは最大フィールドに何も指定しなかった場合、適宜、64 ビット符号付き整数で有効な最小値または最大値が使用されます。 </p> <p> 条件に指定した最小値または最大値が正しく整数値に解析されなかった場合は、ゼロが代わりに使用されます。データセットの処理は中止されません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>最初に、入力フィールドが日付に変換されます。入力フィールドを有効な日付に変換できなかった場合、条件判定の結果は false となります。フィールドを日付に変換できた場合で、なおかつ、指定した最小の日付以降、最大の日付以前の範囲に入力日付が該当した場合のみ、true が返されます。 </p> </td> 
   <td colname="col3"> <p>最小と最大の日付が無効である場合、データセットは構築されません。 </p> <p> 最小または最大の日付を指定しなかった場合、適宜、最小の日付（1600 年 1 月 1 日）または最大の日付（24 世紀におけるいずれかの日付）が代わりに使用されます。 </p> <p> <span class="wintitle">DATETIME</span> には、次のいずれかの形式を使用することをお勧めします。 </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 2013 年 1 月 1 日 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 2013 年 1 月 1 日 HH:MM:SS GMT </li> 
    </ul> <p> タイムゾーンを指定しなかった場合、デフォルトで GMT に設定されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICAL</span> </p> </td> 
   <td colname="col2"> <p>入力フィールドが、辞書式順序において、最小値として指定した文字列以上、最大値として指定した文字列以下である場合にのみ、true が返されます。 </p> </td> 
   <td colname="col3"> <p>辞書式順序に基づく比較には、文字の ASCII 値が使用され、文字列が左から順に 1 文字ずつ比較されます。不一致となった最初の文字について、より大きな ASCII 値を持つ文字列が、もう一方の文字列よりも大きいと見なされます。一方の文字列がもう一方の文字列よりも短いものの、その時点までは、すべての文字が同じであった場合、長い方の文字列がより大きいと見なされます。2 つの文字列が、文字単位ですべて一致しており、長さも完全に等しい場合、辞書式順序において等しいと見なされます。 </p> </td> 
  </tr> 
 </tbody> 
</table>
