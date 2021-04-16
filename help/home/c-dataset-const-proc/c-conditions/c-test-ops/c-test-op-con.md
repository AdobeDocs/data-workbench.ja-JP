---
description: Compare、Not Empty、Range、Regular Expression、String Match など、テスト演算の条件について取り上げます。
title: テスト演算の条件
uuid: 6a117569-1372-4095-972b-76289a45f19e
exl-id: 6c1f521b-a6b9-4bb7-bdfa-56c615b0c916
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 82%

---

# テスト演算の条件{#test-operation-conditions}

Compare、Not Empty、Range、Regular Expression、String Match など、テスト演算の条件について取り上げます。

* [Compare](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac)
* [Not Empty](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)
* [範囲](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1db31583bb09418b8f49481a897b08a6)
* [正規表現](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-ae9c016502cb44128760c58f2d2d5297)
* [String Match](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)

## Compare  {#section-fb2bdb3838504099b324b9838cdeeaac}

[!DNL Compare] は、文字列値または数値を比較する条件です。文字列値を比較する場合、大文字と小文字を区別するかどうかを指定できます。

[!DNL Compare] 条件のパラメーターについて次の表で説明します。

<table id="table_05B1FBB2AED242D99081E62BE2FBEC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Case Sensitive </td> 
   <td colname="col2">true または false。Type が <span class="wintitle">LEXICAL</span> の場合にのみ使用されます。false に設定した場合、大文字と小文字は区別されません。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）条件についてのメモ。 </td> 
   <td colname="col3"> コメント </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input A </td> 
   <td colname="col2"> 比較対象となる 2 つの値の 1 つ目。この値は、条件の左辺オペランドを表します。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input B </td> 
   <td colname="col2"> 比較対象となる 2 つの値の 2 つ目。この値は、条件の右辺オペランドを表します。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>比較演算。利用可能な演算（とその意味）を次に示します。 
     <ul id="ul_74F3C298E9CC4FE89897BA0052A9EB9F"> 
      <li id="li_1605FA73474E404A84056D40E7082623"> = または ==（Input A と Input B が等しい） </li> 
      <li id="li_F694A262ED7A4787B2A68B877339620C"> &lt;&gt; or !=（Input A は Input B と等しくない） </li> 
      <li id="li_1A75437E23B64BEB92297E1C771092B0"> &lt;（Input A は Input B より小さい） </li> 
      <li id="li_B80ED6BE9DEA41FE84BC6BA3B7759276"> &lt;=（Input A は Input B 以下） </li> 
      <li id="li_93148F34065F489E8E198DFB9F9F0E70"> &gt;（Input A は Input B より大きい） </li> 
      <li id="li_8A98EE9AED2445429805169040BB253D"> &gt;=（Input A は Input B 以上） </li> 
     </ul> </p> </td> 
   <td colname="col3"> = </td> 
  </tr> 
  <tr> 
   <td colname="col1"> タイプ </td> 
   <td colname="col2">実行する比較のタイプ。<span class="wintitle">LEXICAL</span>、<span class="wintitle">NUMERIC</span>、<span class="wintitle">DATETIME</span> のいずれかを選択できます。これらのタイプの説明については、「<a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a">テスト演算のテストタイプ</a>」を参照してください。 </td> 
   <td colname="col3"> <span class="wintitle"> LEXICAL</span> </td> 
  </tr> 
 </tbody> 
</table>

この例では、[!DNL Compare]条件を使用して[!DNL Log Entry Condition]を定義しています。 Data Workbench サーバーは、各イベントデータレコードを読み取る際、数値である x-age と 55 を比較します。特定のログエントリについて、x-age が 55 以下である場合、そのログエントリはデータセットの構築プロセスに含められます。

![](assets/cfg_Condition_CompareCondition.png)

## Not Empty {#section-1decb9d887894073a1b6b3d985729ac8}

[!DNL Not Empty] は、フィールドに値が格納されているかどうかをチェックする条件です。[!DNL Input] フィールドの値が空以外であれば、ログエントリがこの条件を満たしていると見なされます。

[!DNL Not Empty] 条件のパラメーターについて次の表で説明します。

| パラメーター | 説明 | デフォルト |
|---|---|---|
| コメント | （オプション）条件についてのメモ。 | コメント |
| Input | 特定のログエントリに関して、値が格納されているかどうかのチェック対象となるフィールドの名前。 |  |

この例では、x-some-field を入力として受け取り、そのフィールドに値が格納されている（空でない）かどうかをテストします。フィールドに値が格納されていれば、条件を満たしたことになります。

![](assets/cfg_Condition_NotEmpty.png)

## 範囲 {#section-1db31583bb09418b8f49481a897b08a6}

[!DNL Range] は、入力フィールドを受け取り、その値が、指定された下限値（Min）パラメーターと上限値（Max）パラメーターの範囲（両端の値を含む）に含まれているかどうかを判断する条件です。

[!DNL Range] 条件のパラメーターについて次の表で説明します。

<table id="table_1587D8D333804FC28024C0DFC2F2D4D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 大文字と小文字を区別 </td> 
   <td colname="col2">true または false。<span class="wintitle">Type</span> が <span class="wintitle">LEXICAL</span> の場合にのみ使用されます。false に設定した場合、大文字と小文字は区別されません。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）条件についてのメモ。 </td> 
   <td colname="col3"> コメント </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 入力 </td> 
   <td colname="col2"> ログエントリからの入力として使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> <p>範囲の下限。 </p> <p> このパラメーターの値は、リテラル値または文字列（つまりフィールド名以外）であることが必要です。このフィールドの日付を使用する場合、タイムゾーンを指定する必要があります。サポートされているタイムゾーンの略称一覧については、 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード</a>. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> <p>範囲の上限。 </p> <p> <p>注意：このパラメーターの値は、リテラル値または文字列（つまりフィールド名以外）であることが必要です。このフィールドの日付を使用する場合、タイムゾーンを指定する必要があります。サポートされているタイムゾーンの略称一覧については、 <a href="../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード</a>. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> タイプ </td> 
   <td colname="col2">実行する比較のタイプ。<span class="wintitle">LEXICAL</span>、<span class="wintitle">NUMERIC</span>、<span class="wintitle">DATETIME</span> のいずれかを選択できます。これらのタイプの説明については、「<a href="../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-types.md#concept-a9fca97a2f03464cb0cbab8b5f809d0a">テスト演算のテストタイプ</a>」を参照してください。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

この例では、[!DNL Range]条件を使用して[!DNL Log Entry Condition]を定義しています。 Data Workbenchサーバーは、各[!DNL event data]レコードを読み取る際、数値x-ageと55を比較します。 特定のログエントリについて、x-age が 55 以上である場合、そのログエントリはデータセットの構築プロセスに含められます。この例で実行される機能は、[!DNL Compare] 条件で取り上げた例と同じです。[Compare](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-fb2bdb3838504099b324b9838cdeeaac) を参照してください。

>[!NOTE]
>
>MinまたはMaxパラメーターを空白のままにした場合、使用可能な最小または最大の整数値が代わりに使用されます。 最小値はゼロ（0）で、最大値は無限です。

![](assets/cfg_Condition_RangeCondition.png)

## 正規表現 {#section-ae9c016502cb44128760c58f2d2d5297}

[!DNL Regular Expression]条件テストでは、正規式のパターンマッチング([正規式](../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)を参照)を使用して、Matchesパラメーターで指定されたパターンのいずれかに一致する文字列が指定された入力フィールドの値に含まれているかどうかを判定します。

入力データが文字列ベクトルである場合、ベクトル内の 1 つ目の値だけがテストに使用されます。[!DNL Regular Expression]条件は、文字列全体を比較します。 文字列を部分的に識別する必要がある場合は、文字列の前後に「.*」を付加する必要があります。

[!DNL Regular Expression] 条件のパラメーターについて次の表で説明します。

<table id="table_0BF5F89F87C9493B8DABA97620074FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 大文字と小文字を区別 </td> 
   <td colname="col2"> true または false。false に設定した場合、大文字と小文字は区別されません。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）条件についてのメモ。 </td> 
   <td colname="col3"> コメント </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 入力 </td> 
   <td colname="col2"> ログエントリからの入力として使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matches </td> 
   <td colname="col2"> <p>入力フィールドの値と突き合わせる正規表現パターン（複数可）。 </p> <p> <b>正規表現パターンを追加するには</b> 
     <ol id="ol_6D6467FF74334DEA8E8625C3B155D11D"> 
      <li id="li_9E13A63558FF44749C2E49BD50B7F770"><span class="uicontrol">Matches</span> を右クリックします。 </li> 
      <li id="li_195A2F3B6B9442F5B1DACDE0FC96CE5C"><span class="uicontrol">新規追加</span>／<span class="uicontrol">Regular Expression</span> をクリックします。 </li> 
      <li id="li_225E98F8EF39426A9483B86EA2CFE6DF">目的の正規表現をテキストボックスに入力します。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

以下に示したのは、Web サイトトラフィックから収集したデータのフィールドに、[!DNL Regular Expression] 条件を適用して、一致しているかどうかを判断する例です。この条件は、cs(転送者クエリ)フィールドに、正規式`campaign=C[1-9][0-9]{4}`と一致する文字列が含まれている場合にのみtrueを返します。 この正規式は、`campaign=C12345`を含む任意の文字列と一致します。 ただし、`C`の後の最初の文字が`1-9`の範囲にないので、`campaign=C0123&`という文字列とは一致しません。

![](assets/cfg_Condition_RegularExpression.png)

## String Match {#section-f8d132085c6b4500bfbe4515b848142f}

[!DNL String Match]条件は、文字列の等価性をテストします。 指定されたフィールドを入力として受け取り、各ログエントリ内のフィールドの値と、この条件演算の Matches パラメーターに指定された文字列とを比較します。Matches に指定されたいずれかの文字列が、指定された入力フィールドの値と同じ（大文字と小文字が区別されます）である場合、true を返します。[!DNL StringCondition] に一致文字列が存在しない場合は、false を返します。入力データが文字列ベクトルである場合、ベクトル内の 1 つ目の値（文字列）だけがテストに使用されます。

<table id="table_BD599BAA5DD54B278813B6C38AC8DE6B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
   <th colname="col3" class="entry"> デフォルト </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 大文字と小文字を区別 </td> 
   <td colname="col2"> true または false。false に設定した場合、大文字と小文字は区別されません。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> コメント </td> 
   <td colname="col2"> （オプション）条件についてのメモ。 </td> 
   <td colname="col3"> コメント </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 入力 </td> 
   <td colname="col2"> ログエントリからの入力として使用するフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一致 </td> 
   <td colname="col2"> <p>入力フィールドの値と突き合わせる文字列（複数可）。 </p> <p> <b>文字列を追加するには</b> 
     <ol id="ol_9E32218C771445D88357960475FAD6EB"> 
      <li id="li_A700747858D0470491783E9B3933DAFE"><span class="uicontrol">Matches</span> を右クリックします。 </li> 
      <li id="li_9D1A2462EA404B0F84426176737CAFED"><span class="uicontrol">新規追加</span>／<span class="uicontrol">String</span> をクリックします。 </li> 
      <li id="li_E84D2439B59548E5B1803C64A295A18E">目的の文字列をテキストボックスに入力します。 </li> 
     </ol> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

以下に示したのは、Web サイトトラフィックから収集したデータに [!DNL String Match] 条件を適用する例です。この条件は、入力フィールド(cs-uri-stem)がMatchesパラメーターで指定された2つの文字列のいずれかに一致するかどうかをテストし、フィールドcs-uri-stemが正確な文字列[!DNL /navigation/footer.asp]または完全な文字列[!DNL /navigation/header.asp]のいずれかである場合に成功します。

![](assets/cfg_Condition_StringMatch.png)
