---
description: Split 変換は、特定の区切り文字に基づいて 1 つの文字列を複数のサブ文字列のベクトルに分割します。
solution: Analytics
title: Split
topic: Data workbench
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Split{#split}

Split 変換は、特定の区切り文字に基づいて 1 つの文字列を複数のサブ文字列のベクトルに分割します。

[!DNL Split] は、特に、単一の URI クエリー名の値に関連付けられた値の集合から個々の値を抽出する場合に便利です。

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments </td> 
   <td colname="col2"> (オプション)変換についてのメモ。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition </td> 
   <td colname="col2"> この変換が適用される条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimiter </td> 
   <td colname="col2"> <p>入力文字列をサブ文字列に分割する際に使用する文字列。長さは 1 文字とする必要があります。 </p> <p> Delimiter パラメーター内で Ctrl キーを押しながら右クリックすると、挿入メニューが表示されます。このメニューには、区切り文字としてよく使用される特殊文字が一覧表示されます。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> 入力フィールドの名前。このフィールドの値が分割されて、出力文字列ベクトルが作成されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> 出力フィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

ある Web サイトは、顧客が購入を確定しようと確認ページにアクセスすると、該当製品が cs-uri-query 値の中で列挙されます。以下に示したのは、そのような文字列の例です。

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

リクエストされたページが確認ページであるかどうかは、ログエントリの cs-uri-stem フィールドを使用して判断します。顧客の購入した製品のコードは、prod_selected を名前とするコンマ区切りの値として cs-uri-query に列挙されます。この情報は、[!DNL Split] 条件に指定された値と cs-uri-stem の値が一致したとき、[!DNL String Match] 変換を使用して製品コードをコンマで分割することによって抽出できます。String Match について詳しくは、[String Match](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f) を参照してください。この要件は、以下の変換によって解決できます。

![](assets/cfg_TransformationType_Split.png)

出力フィールドは x-products です。購入が確定されたセッション期間と購入製品とをマッピングする拡張ディメンションが必要であれば、このフィールドを使用して作成できます。
