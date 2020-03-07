---
description: Math 変換すると、ログエントリ内のフィールドに対して算術演算を適用できます。
solution: Analytics
title: Math
topic: Data workbench
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Math{#math}

Math 変換すると、ログエントリ内のフィールドに対して算術演算を適用できます。

例えば、10 進数の整数や浮動小数点の定数を演算の対象とすることができます。

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
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
   <td colname="col1"> 式 </td> 
   <td colname="col2"> <p>実行する計算を表す演算式。 </p> <p> 以下に示した任意の演算および関数を使用でき、式にはフィールド名を含めることができます。 </p> <p> 演算 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> 加算（+） </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> 減算（-） </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> 乗算（*） </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> 除算（/） </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> 剰余（%） </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> 累乗法 (^) </li>
     </ul></p> <p>関数 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x)：x が正数の場合は 1 を、x がゼロの場合は 0 を、x が負数の場合は -1 を返します。 </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x)：x の絶対値を返します。 </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x)：x 以下の最大の整数を返します。 </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x)：x に最も近い整数を返します。 </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x)：b を底とする x の対数を返します。 </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,...)：すべての引数の中で最も小さいものを返します。 </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...)：すべての引数の中で最も大きいものを返します。 </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> 算術演算の結果を格納するフィールドの名前。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

次の例は、Web サイトトラフィックから収集されたデータのフィールドを使用するものです。x-timestamp から x-last-pv-timestamp を減算したうえで 1 を加算することによって、x-page-duration という名前の新しいフィールドを計算します。出力結果が計算されるのは、ユーザー定義フィールド x-last-pv-timestamp（訪問者が最後にページを表示したときのタイムスタンプ）に値が存在する（つまり「not empty」である）ときだけです。

![](assets/cfg_TransformationType_Math.png)

条件について詳しくは、「 [!DNL Not Empty] 条件」を参照して [ください](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。
