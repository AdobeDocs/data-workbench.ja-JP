---
description: Web データを扱う際、クエリー文字列や cookie などの形式でエンコードされたフィールドの値を、ExtractValue 変換を使用して Web サイトデータから抽出することができます。
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

Web データを扱う際、クエリー文字列や cookie などの形式でエンコードされたフィールドの値を、ExtractValue 変換を使用して Web サイトデータから抽出することができます。

抽出対象の値に対応する名前は、ログエントリごとに異なる場合があります。

<table id="table_D16A39BE035043628A4D6F7452952304"> 
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
   <td colname="col1"> Input Name </td> 
   <td colname="col2"> <p>Input Query から抽出するフィールドの名前。 </p> <p> <p>注意：Input Name がベクトルである（つまり、複数の名前を含んでいる）場合、抽出される値は 1 つだけです。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Query </td> 
   <td colname="col2"> 値の抽出元となるエンコードされたマッピング（クエリー文字列、cookie など）。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Value </td> 
   <td colname="col2"> 抽出されたデコード済みの値を取り込むフィールドの名前。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

検索語句を抽出する場合、その語句全体を抽出し、必要に応じて、[!DNL Tokenize] 変換を使用し、検索キーワードに分割することができます。変換について詳しくは、 [!DNL Tokenize] Tokenizeを参照して [ください](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c)。

次に示したのは、cs(referrer-query) から x-v-search-querynames フィールドの値を抽出し、x-search-phrase フィールドに格納する [!DNL ExtractValue] 変換の設定例です。

![](assets/cfg_TransformationType_ExtractValue.png)

