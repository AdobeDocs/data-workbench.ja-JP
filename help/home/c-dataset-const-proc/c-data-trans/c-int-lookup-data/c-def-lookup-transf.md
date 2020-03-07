---
description: ルックアップデータをデータセットに組み入れる際に利用できる変換について取り上げます。
solution: Analytics
title: ルックアップ変換の定義
topic: Data workbench
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ルックアップ変換の定義{#defining-lookup-transformations}

ルックアップデータをデータセットに組み入れる際に利用できる変換について取り上げます。

データセット構築プロセスの 2 つの段階の一方でしか使用できないタイプの変換もあるので注意してください。

* [Categorize](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## Categorize {#section-8474376c14e54d14ae73749696ada468}

[!DNL Categorize] 変換には、パターン文字列と値のペアから成る 2 列のルックアップテーブルを使用します。この変換では、Data Workbench サーバーが個々のイベントデータレコードを順に読み取り、そのレコード内の指定されたフィールドの内容を、ルックアップテーブルの 1 列目にリストされた各パターン文字列と比較します。指定されたフィールドがいずれかのパターン文字列と一致した場合、対応する値（2 列目の内容）を、レコード内の指定された出力フィールドに書き込みます。

パターンの先頭または末尾との比較を強制するために、ルックアップテーブルの 1 列目の文字列は、必要に応じて先頭に ^ 文字を、末尾に $ 文字を使用することができます。この変換では、1 列目に正規表現を使用して一致条件を定義することはできません。入力値が文字列ベクトルであった場合は、各文字列に変換が適用され、出力文字列ベクトルにその結果が付加されます。

同じことを [!DNL Categorize] 変換で行うこともできますが、通常は、[!DNL Regular Expression] 変換を使用した方が簡単で高速に実行することができます。

>[!NOTE]
>
>The substring test used in [!DNL Categorize] is case-sensitive unless otherwise specified using the [!DNL Case Sensitive] parameter.

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
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
   <td colname="col1"> Case Sensitive </td> 
   <td colname="col2"> true または false。サブ文字列テストで大文字と小文字を区別するかどうかを指定します。 </td> 
   <td colname="col3"> true </td> 
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
   <td colname="col1"> Default </td> 
   <td colname="col2"> 条件判定に成功したがカテゴリー化ファイルのいずれのエントリも入力と一致しなかった場合、または指定されたログエントリに入力フィールドが定義されていなかった場合に使用されるデフォルト値。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimiter </td> 
   <td colname="col2"> <p>ルックアップファイル内の列の区切りに使用する文字列。長さは 1 文字とする必要があります。 </p> <p> Delimiter パラメーター内で Ctrl キーを押しながら右クリックすると、<span class="wintitle">挿入</span>メニューが表示されます。このメニューには、区切り文字としてよく使用される特殊文字が一覧表示されます。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values </td> 
   <td colname="col2"> true または false。true の場合、入力に一致する行がファイル内に複数見つかると、値に含まれる各一致結果が出力文字列ベクトルに付加されます。false の場合、ファイル内の最初に一致した行だけが出力に使用されます。後者のケースで、入力がベクトルであった場合、出力も同じ長さのベクトルになります。入力が単純な文字列であった場合は、出力も単純な文字列になります。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> カテゴリー化ファイルのパスとファイル名。相対パスの基準は、Data Workbench サーバーのインストールディレクトリです。このファイルは、一般に、Data Workbench サーバーのインストールディレクトリにある Lookups ディレクトリに格納されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> このフィールドの値に対して、カテゴリー化ファイル内のサブ文字列が比較されて、一致する行が特定されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output </td> 
   <td colname="col2"> 結果に関連付けられているフィールドの名前。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**Categorizeの考慮事項**

* Changes to lookup files in [!DNL Categorize] transformations defined in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file require retransformation of the dataset. Lookup files for [!DNL Categorize] transformations defined in the [!DNL Log Processing.cfg] file or a [!DNL Log Processing Dataset Include] file are not subject to this limitation. データの再処理について詳しくは、再処理と再変換 [を参照してください](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL Categorize] ファイルまたはファイルで定 [!DNL Log Processing.cfg] 義された変換は、ルッ [!DNL Log Processing Dataset Include] クアップファイルが変更されるたびに、そのルックアップファイルを再読み込みします。 過去にさかのぼって変更が適用されることはありませんが、その変更が行われた後に読み込まれたログデータにはすべて変更が適用されます。

以下に示したのは、Web サイトトラフィックから収集したイベントデータに、[!DNL Categorize] 変換を使用してルックアップデータを統合する例です。特定の Web サイトにいくつかのビジネスセクションがあって、各セクションのトラフィックフローと生み出された価値に基づいて比較検討できるようにしたいとします。この場合、ルックアップファイルを作成して、各セクションを識別するためのサブ文字列をリストします。

The lookup file [!DNL Lookups\custommap.txt] contains the following table:

| /products/ | 製品 |
|---|---|
| ^/sports/ | Sports |
| ^/news/ | News |
| ： | ： |

このカテゴリー化ファイルは、「/products/」という文字列を含んだすべての値を「Products」という値にマッピングします。また、「/sports/」で始まる値を「Sports」という値に、「/news/」で始まる値を「News」という値にマッピングします。次のカテゴリー化変換は、cs-uri-stem フィールドの値を入力として使用します。つまり、このフィールド内の文字列から、サブ文字列との一致を検索することになります。変換の結果は、x-custommap フィールドに格納されます。

![](assets/cfg_TransformationType_Categorize.png)

Multiple Values パラメーターが false に設定されていると仮定した場合、cs-uri-stem の一連の値に対して x-custommap には次の値が生成されます。

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | Sports |
| [!DNL /sports/products/buy.php] | 製品 |
| [!DNL /news/headlines.php] | News |
| [!DNL /news/products/subscribe.php] | 製品 |

出力結果は、ルックアップファイル内のサブ文字列の順序に左右されます。For example, the cs-uri-stem [!DNL /sports/products/buy.php] returns &quot;Products.&quot; URI ステムは「/sports/」で始まっていますが、ルックアップファイルには「/products/」が「/sports/」よりも先に記述されています。仮に Multiple Values パラメーターが true に設定された場合、x-custommap には、別の値が追加されることになります。最後の例で言えば、ルックアップテーブル内の 2 つの行（Products と News）が一致します。

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

[!DNL FlatFileLookup] 変換には、任意の数の列と行で構成されたルックアップテーブルが使用されます（ただし、ルックアップテーブルはメモリ内に常駐します）。このタイプの変換では、Data Workbench サーバーが個々のイベントデータレコードを順に読み取り、そのレコード内の指定されたフィールドの内容を、ルックアップテーブル内の指定された列の各値と比較します。一致が見つかった場合、Data Workbench サーバーは、ルックアップテーブル内の一致した行の 1 つまたは複数の値を、イベントデータレコード内の指定された 1 つまたは複数の出力フィールドに書き込みます。

この変換で使用されるルックアップテーブルの内容は、フラットファイルから入力されます。フラットファイルの場所は、変換を定義するときに指定します。

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
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
   <td colname="col1"> Default </td> 
   <td colname="col2"> 条件が満たされたが、入力と一致するエントリがルックアップファイルに存在しなかった場合に使用されるデフォルト値。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Delimiter </td> 
   <td colname="col2"> <p>ルックアップファイル内の列の区切りに使用する文字列。長さは 1 文字とする必要があります。 </p> <p> Delimiter パラメーター内で Ctrl キーを押しながら右クリックすると、<span class="wintitle">挿入</span>メニューが表示されます。このメニューには、区切り文字としてよく使用される特殊文字が一覧表示されます。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> File </td> 
   <td colname="col2"> ルックアップファイルのパスとファイル名。相対パスの基準は、Data Workbench サーバーのインストールディレクトリです。このファイルは、一般に、Data Workbench サーバーのインストールディレクトリにある Lookups ディレクトリに格納されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Header Row </td> 
   <td colname="col2"> true または false。テーブルの先頭行がヘッダー行であり、処理から除外することを指定します。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input </td> 
   <td colname="col2"> <span class="wintitle">Column Name</span> は、入力データをファイル内の行と突き合わせる際に使用する列の名前です。Header Row が true である場合、ルックアップファイル内の列の名前を指定できます。それ以外の場合、突き合わせる列の 0 ベースの番号を指定する必要があります。<span class="wintitle">Field Name</span> は、ルックアップファイル内の行を特定する際に使用するフィールドの名前です。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values </td> 
   <td colname="col2"> <p>true または false。単一の値（一致行）を返すか、複数の値（一致行ごとに 1 つ）を返すかを指定します。 </p> <p> <p>注意：<span class="wintitle">Multiple Values</span> を false に設定する場合は、複数の一致が生じないよう注意してください。複数の一致が見つかった場合にどれが返されるかは保証されません。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Outputs </td> 
   <td colname="col2"> <p>列オブジェクト（結果）のベクトル。ベクトル内の各オブジェクトは、列名とフィールド名で定義されます。 </p> <p> <span class="wintitle">Column Name</span> は、出力値の取得元となる列です。<span class="wintitle">Header Row</span> が true である場合、ルックアップファイル内の列の名前を指定できます。それ以外の場合、突き合わせる列の 0 ベースの番号を指定する必要があります。 </p> <p> <span class="wintitle">Field Name</span> は、出力結果を取り込むフィールドの名前です。Multiple Values パラメーターを true に設定した場合、それぞれの行につき 1 件の結果を格納するベクトルを指定することができます。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**考慮事項：[!DNL FlatFileLookup]**

* 入力フィールドとルックアップファイルとの比較では常に、大文字と小文字が区別されます。
* Changes to lookup files in [!DNL FlatFileLookup] transformations defined in the [!DNL Transformation.cfg] file or [!DNL Transformation Dataset Include] files require retransformation of the dataset. ファイル内で定義さ [!DNL FlatFileLookup] れた変換の参照フ [!DNL Log Processing.cfg] ァイルは、 [!DNL Log Processing Dataset Include] この制限の対象となりません。 データの再処理について詳しくは、再処理と再変換 [を参照してください](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL FlatFileLookup] ファイル内の変換は、ル [!DNL Log Processing.cfg] ックアップフ [!DNL Log Processing Dataset Include] ァイルが変更されるたびに、ルックアップファイルをリロードします。 過去にさかのぼって変更が適用されることはありませんが、その変更が行われた後に読み込まれたログデータにはすべて変更が適用されます。

以下に示したのは、Web サイトトラフィックから収集したイベントデータに、[!DNL FlatFileLookup] 変換を使用してルックアップデータを統合する例です。その Web サイトへのトラフィックルーティングに寄与している Web サイトパートナーを見つけ出して、そのパートナー ID を、よりわかりやすい名前に変換したいとします。そうすると、トラフィックのルーティングに使われているサイト間の関係よりも明確にビジネス上の関係を表現する拡張ディメンションとビジュアライゼーションを、そのわかりやすい名前を使用して作成できます。

この例に示した変換は、cs(referrer-query) フィールドから PartnerID の名前と値のペアを検索し、見つかった場合は、ルックアップファイル [!DNL Lookups\partners.txt] を使用して、PartnerID の値とテーブルの [!DNL Partner] 列の値とを比較します。一致する行が見つかった場合、出力フィールド x-partner-name に、特定された行の [!DNL PrintName] 列の名前が割り当てられます。

![](assets/cfg_TransformationType_FlatFileLookup.png)

例えば、ルックアップテーブルに次の情報が格納されているとします。

| ID | Partner | Started | PrintName |
|---|---|---|---|
| 1 | P154 | Aug 21, 1999 | Yahoo |
| 2 | P232 | July 10, 2000 | Microsoft |
| 3 | P945 | Jan 12, 2001 | Amazon |

次の例は、次のように変換されます。

* cs(referrer)(PartnerID) から P232 が返された場合、x-partner-name フィールドには「Microsoft」という値が割り当てられます。
* cs(referrer)(PartnerID) から P100 が返された場合、x-partner-name フィールドには「No Partner」という値が割り当てられます。
* cs(referrer)(PartnerID) から何も返されなかった場合、x-partner-name フィールドには、Default パラメーターの指定に従って「No Partner」という値が割り当てられます。

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

The [!DNL ODBCLookup] transformation operates like a [!DNL FlatFileLookup] transformation. 唯一違うのは、変換時に使用されるルックアップテーブルの内容が、フラットファイルからではなく、ODBC データベースから入力されるという点です。

>[!NOTE]
>
>[!DNL ODBCLookup] 変換は、データセット構築プロセスの変換段階でのみ実行できます。 可能であれば、[!DNL FlatFileLookup] 変換ではなく [!DNL ODBCLookup] 変換を使用することをお勧めします。外部システムの利用の可否に依存しないという点で、[!DNL FlatFileLookup] 変換の方が信頼性に優れています。加えて、ルックアップテーブルのあるフラットファイルがローカルで管理されていれば、ルックアップテーブルが変更されるリスクも小さくて済みます。

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
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
   <td colname="col1"> Data Source Name </td> 
   <td colname="col2"> データの読み込み元のデータベースを指定する DSN。DSN は、データセットの処理が実行される Data Workbench サーバーコンピューターの管理者に支給を依頼してください。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database Password </td> 
   <td colname="col2">データベースへの接続に使用するパスワード。<span class="wintitle">データソースアドミニストレーター</span>で DSN のパスワードが設定済みである場合は空欄でも構いません。ここに指定したパスワードは、<span class="wintitle">データソースアドミニストレーター</span>で設定されている DSN のパスワードよりも優先されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database User ID </td> 
   <td colname="col2">データベースへの接続に使用するユーザー ID。<span class="wintitle">データソースアドミニストレーター</span>で DSN のユーザー ID が設定済みである場合は空欄でも構いません。ここに指定したユーザー ID は、<span class="wintitle">データソースアドミニストレーター</span>で設定されている DSN のユーザー ID よりも優先されます。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Default </td> 
   <td colname="col2"> 条件が満たされたが、入力と一致するエントリがルックアップファイルに存在しなかった場合に使用されるデフォルト値。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Column </td> 
   <td colname="col2"> <span class="wintitle">Column Name</span> は、入力データと突き合わせるデータの列名または SQL 式です。<span class="wintitle">Field Name</span> は、検索するデータが格納されているフィールドの名前です。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Multiple Values </td> 
   <td colname="col2"> <p>true または false。単一の値（一致行）を返すか、複数の値（一致行ごとに 1 つ）を返すかを指定します。 </p> <p> <p>注意：<span class="wintitle">Multiple Values</span> を false に設定する場合は、複数の一致が生じないよう注意してください。複数の一致が見つかった場合にどれが返されるかは保証されません。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Columns </td> 
   <td colname="col2"> <p>列オブジェクト（結果）のベクトル。ベクトル内の各オブジェクトは、列名とフィールド名で定義されます。 </p> <p> <span class="wintitle">Column Name</span> は、出力値の取得元となる列の名前または SQL 式です。<span class="wintitle">Field Name</span> は、出力結果を取り込むフィールドの名前です。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Table Identifier</span> </td> 
   <td colname="col2"> 読み込むデータが格納されているテーブルまたはビューを指定する SQL 式。標準的なテーブル ID の形式は SCHEMA.TABLE です。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* The Data Source Name, [!DNL Database User ID], [!DNL Database Password], and Table Identifier parameters are the same as the parameters of the same names that are described for ODBC data sources. See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* ODBC データソースとは異なり、[!DNL ODBCLookup] 変換には、インクリメントする ID 列は不要です。See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). なぜなら、データセットがアクティブである間は、どのような形であれ、ルックアップテーブルの内容に変更が生じることは許されないためです。ルックアップテーブル（またはビュー）への変更は、再変換が実行されるまで検出されません。データの再処理について詳しくは、[再処理と再変換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)を参照してください。

古くなった DNS レコードを最新のレコードに変換したいとします。どちらのレコードも SQL データベースに格納されています。この作業を行うには、そのデータベースから生成されたルックアップテーブルを参照して、古い DNS レコードを置き換える必要があります。

この場合、ログエントリから s-dns フィールドを検索し、見つかった s-dns エントリと、ルックアップテーブル VISUAL.LOOKUP の [!DNL OLDDNS] 列内のエントリとを比較します。テーブル内の行が特定された場合、その行の [!DNL NEWDNS] 列から最新の DNS レコードエントリを取得し、出力フィールド s-dns に割り当てます。

![](assets/cfg_TransformationType_ODBCLookup.png)

