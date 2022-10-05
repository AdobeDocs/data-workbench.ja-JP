---
description: Merge 変換は、入力フィールド（通常は文字列ベクトル）から値を受け取って、指定された区切り文字で単一の文字列に結合し、指定された出力フィールドにその結果を格納します。
title: Merge
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 90%

---

# 結合{#merge}

{{eol}}

Merge 変換は、入力フィールド（通常は文字列ベクトル）から値を受け取って、指定された区切り文字で単一の文字列に結合し、指定された出力フィールドにその結果を格納します。

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）。変換についてのメモ。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> この変換が適用される条件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> デフォルト </td> 
   <td colname="col2"> デフォルト値。条件が満たされたが、入力値が利用できない場合に使用されます。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 区切り </td> 
   <td colname="col2"> <p>入力文字列ベクトルの個々のエレメントを単一の出力文字列内で区切るための文字列。 </p> <p> Delimiter パラメーター内で Ctrl キーを押しながら右クリックすると、<span class="wintitle">挿入</span>メニューが表示されます。このメニューには、区切り文字としてよく使用される特殊文字が一覧表示されます。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> 出力文字列の構成要素となる文字列値のベクトル。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 出力 </td> 
   <td colname="col2"> 出力文字列の名前。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

次の例では、文字列の入力ベクトルに、購入対象として選択された一連の製品が含まれていることを前提としています。これらの製品が「::」（コロン 2 つ）で区切られて単一の出力文字列に結合されます。

![](assets/cfg_TransformationType_Merge.png)

したがって、入力フィールド x-products にB57481、C46355、Z97123という文字列値が含まれている場合、出力文字列 x-show-products は次のようになりB57481す。:C46355::Z97123.
