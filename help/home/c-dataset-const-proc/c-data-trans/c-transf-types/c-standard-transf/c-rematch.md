---
description: REMatch 変換は、入力データから検索して捕捉する 1 つまたは複数のパターンを正規表現で指定するパターンマッチング変換です。
solution: Analytics
title: REMatch
topic: Data workbench
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# REMatch{#rematch}

REMatch 変換は、入力データから検索して捕捉する 1 つまたは複数のパターンを正規表現で指定するパターンマッチング変換です。

この変換では、正規表現で捕捉するサブパターンごとに出力フィールドが構築されます。正規表現が入力フィールドと一致しない場合、出力結果はブランクとなります。出力フィールドが既に存在する場合、その値がブランク値で置き換えられます。正規表現の簡単な使用法については、 [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>この変 [!DNL REMatch] 換の動作は、変換と同 [!DNL RETransform] 様です( [RETransformを参照](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74))。この変換では、正規表現を使用して文字列を取り込み、その文字列を単一の出力フィールドに格納します。

[!DNL REMatch] 複数の変換や1つの変換の後に変換が続く [!DNL RETransform] よりも効率的に [!DNL RETransform] 文字列を解析でき [!DNL Flatten] ます。 分割・統合を参 [照してくださ](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce)い。

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col1"> Case Sensitive </td> 
   <td colname="col2"> true または false。マッチングで大文字と小文字を区別するかどうかを指定します。 </td> 
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
   <td colname="col2"> マッチングに使用する正規表現。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> 正規表現に照らして評価されるフィールド。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Outputs </td> 
   <td colname="col2"> <p>出力文字列または出力ベクトルの名前。入力として文字列ベクトルを受け取った場合、出力も文字列ベクトルになります。 </p> <p> 正規表現で捕捉するサブパターンごとに出力フィールドが存在している必要があります。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] 変換は非常に遅くなり、データの処理時間の大部分を占める場合があります。

次の例では、YYYY-MM-DD 形式の日付を [!DNL REMatch] 変換で解析し、x-year、x-month、x-day の各フィールドに格納しています。2007-01-02 という日付の場合、x-year、x-month、x-day に格納される値は、それぞれ 2007、01、02 となります。

![](assets/cfg_TransformationType_REMatch.png)

