---
description: Format 変換は一連の入力を受け取って、指定された構造と一致するように出力の書式を整えます。
solution: Analytics
title: 形式
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 形式{#format}

Format 変換は一連の入力を受け取って、指定された構造と一致するように出力の書式を整えます。

この変換は、単純文字列または文字列ベクトルに対して作用します。指定された書式を個々の入力値に適用し、すべての入力値を変換したうえで出力結果を生成します。

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> Comments </td> 
   <td colname="col2"> (オプション)変換についてのメモ。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> この変換が適用される条件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 形式 </td> 
   <td colname="col2"> <p>出力の体裁を指定するための書式設定文字列。 </p> <p> %1% は 1 つ目の入力ベクトルの値を、%2% は 2 つ目の入力ベクトルの値を表します（以降同様）。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inputs </td> 
   <td colname="col2"> <p>単純文字列または文字列ベクトルが格納されているフィールド。文字列ベクトルを入力とした場合、出力も文字列ベクトルとなります。それぞれの一連の入力値に <span class="wintitle">Format</span> パラメーターを適用することによって得られます。 </p> <p> <p>注意：入力の番号は 0 から始まりますが、書式の置換値は %1% から始まります。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> 変換結果を格納するために作成されるフィールドの名前。入力が文字列ベクトルである場合、出力文字列ベクトルの長さは、最長の入力ベクトルの長さと等しくなります。それよりも短い文字列ベクトルが入力に含まれている場合、書式設定文字列内の対応する位置に空の文字列を使用して出力ベクトルの長さが揃えられます。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

次の例では、2 つのベクトル（製品のカテゴリーを表す文字列ベクトルと、購入製品ごとの数量を表す対応する文字列ベクトル）が、「Product %1%, Quantity %2%」という形式を持つ同じ長さの単一のベクトルに変換されます。

![](assets/cfg_TransformationType_Format.png)

製品カテゴリーを表す入力ベクトルが (683, 918) で、数量を表す入力ベクトルが (10, 4) である場合、変換結果は、(&quot;Product 683, Quantity 10&quot;, &quot;Product 918, Quantity 4&quot;) という 2 つの文字列を格納した単一の出力ベクトルとなります。
