---
description: REMatch 変換は、入力データから検索して捕捉する 1 つまたは複数のパターンを正規表現で指定するパターンマッチング変換です。
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 79%

---

# REMatch{#rematch}

REMatch 変換は、入力データから検索して捕捉する 1 つまたは複数のパターンを正規表現で指定するパターンマッチング変換です。

この変換では、正規表現で捕捉するサブパターンごとに出力フィールドが構築されます。正規表現が入力フィールドと一致しない場合、出力結果はブランクとなります。出力フィールドが既に存在する場合、その値がブランク値で置き換えられます。正規表現の簡単な使用法については、 [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>[!DNL REMatch]変換の動作は、[!DNL RETransform]変換（[RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)を参照）と同じです。この変換では、正規式を使用して文字列を取得し、その文字列を単一の出力フィールドに格納します。

[!DNL REMatch] 複数の [!DNL RETransform] 変換や、1つの変換の後に変換が続く1つの変換よりも、文字列をより効率的に解析でき [!DNL RETransform]  [!DNL Flatten] ます。[Flatten](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce)を参照してください。

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
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）変換についてのメモ。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
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
>[!DNL REMatch] 変換は非常に遅くなる可能性があり、データの処理時間の大部分が、変換に費やされる可能性があります。

次の例では、YYYY-MM-DD 形式の日付を [!DNL REMatch] 変換で解析し、x-year、x-month、x-day の各フィールドに格納しています。2007-01-02 という日付の場合、x-year、x-month、x-day に格納される値は、それぞれ 2007、01、02 となります。

![](assets/cfg_TransformationType_REMatch.png)
