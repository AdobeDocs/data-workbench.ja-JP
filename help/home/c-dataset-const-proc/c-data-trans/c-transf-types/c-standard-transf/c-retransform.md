---
description: RETransform（正規表現）変換は、入力データから検索して捕捉するパターンを正規表現で記述し、指定された出力フィールドに捕捉した文字列を格納するパターンマッチング変換です。
solution: Analytics
title: RETransform
topic: Data workbench
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# RETransform{#retransform}

RETransform（正規表現）変換は、入力データから検索して捕捉するパターンを正規表現で記述し、指定された出力フィールドに捕捉した文字列を格納するパターンマッチング変換です。

正規表現の評価は、入力文字列全体に対して行われます。正規表現で指定されたパターンと入力が一致しない場合、データは捕捉されません。正規表現の簡単な使用法については、 [正規表現](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>この変 [!DNL RETransform] 換は、正規表現で取り込 [!DNL REMatch] む各サブパターンの出力フィールドを構築する変換( [REMatchを参照](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e))と同様に動作します。 You can think of [!DNL RETransform] as a combination of [!DNL REMatch] and [!DNL Format] transformations. Action パラメーター（以下の表の「Action」を参照）が「RESULTS」に設定されている場合、[!DNL RETransform] は、[!DNL REMatch] 変換と [!DNL Union] 変換を組み合わせたような動作になります。

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
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
   <td colname="col1"> Default </td> 
   <td colname="col2"> デフォルト値。条件が満たされたが、入力値が利用できない場合、または正規表現が入力値と一致しない場合に使用されます。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> アクション </td> 
   <td colname="col2"> <p>結果の処理方法を指定します。デフォルトの設定（RESULTS）では単に、マッチングで抽出されたパターンから文字列のベクトルが作成されます。 </p> <p> また、書式設定文字列をアクションとして指定することもできます。特定の形式の単純な文字列出力を作成することが可能です。この方法では、一致した各パターンの位置に対応する番号を % 記号で囲んで指定します。例えば、一致した最初のパターンは %1% に、3 番目のパターンは %3% になります。それ以外の文字は、書式設定文字列の中でリテラルに指定します。 </p> </td> 
   <td colname="col3"> RESULTS </td> 
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
   <td colname="col1"> Output </td> 
   <td colname="col2"> 出力文字列の名前。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] 変換は非常に遅くなり、データの処理時間の大部分を占める場合があります。

次の例では、Web サイトの訪問者が使用している Windows オペレーティングシステムのバージョンを抽出し、その値から x-windows-version フィールドを作成します。このケースでは、バージョン番号だけが出力値として得られます。

![](assets/cfg_TransformationType_RegularExpression.png)

読みやすくするために、バージョン番号の前に「Version」という文字列を追加したい場合は、Action パラメーターを「RESULTS」から「Version %1%」に変更します。リテラルのパーセント記号（%）を出力に含めるには、「%%」のように、パーセント記号をもう 1 つ追加してエスケープします。
