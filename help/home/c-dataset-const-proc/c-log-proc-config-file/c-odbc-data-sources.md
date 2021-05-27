---
description: Data Workbench サーバー（InsightServer64.exe）は、ドライバーが ODBC 3.0 に準拠していれば SQL データベース（Oracle、Microsoft SQL Server など）からイベントデータを読み取ることもできます。
title: ODBC データソース
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 91%

---

# ODBC データソース{#odbc-data-sources}

Data Workbench サーバー（InsightServer64.exe）は、ドライバーが ODBC 3.0 に準拠していれば SQL データベース（Oracle、Microsoft SQL Server など）からイベントデータを読み取ることもできます。

Data Workbench サーバーの ODBC 対応は、Sensor から、または外部処理で生成されたログファイルからデータを読み込むための既存の機能と大きな違いはありません。ただし、特別に考慮する必要のある事柄と制限が存在します。

* Data Workbench サーバーの ODBC 対応機能はクラスタリング機能に適合しています。データをすべての処理サーバーに分散すると、以後すべての処理（クエリー処理を含む）で、クラスタリングの利点を最大限に活用できます。
* ODBC 対応は、サードパーティの ODBC ドライバーに依存します。ODBC 対応機能が正しく動作するためには、それらのドライバーが、Data Workbench サーバーを実行するコンピューターに対し、アドビプラットフォーム以外のツールを使って設定されている必要があります。Data Workbench コンピューターについては特別な設定は不要です。
* データの読み込み元となるテーブルまたはビューには、インクリメントする ID 列が必要です。データベースに新しい行が挿入されたときに、どの行においても、この列（テーブル内の実際の列または SQL の列式）の値が減少することは許されません。この制約に違反した場合、データが失われます。適切なパフォーマンスを確保するためには、この列または列式にインデックスが必要です。

   >[!NOTE]
   >
   >[!DNL Increasing ID]列には、複数の行に同じ値を指定できます。 例えば、タイムスタンプ列の有効桁数が不十分だとそのようなことが起こります。

* Data Workbench サーバーは、長大なデータ（実際に使用するデータベースアプリケーションで決められた長さを超えるデータ）が格納された列を読み込むことができません。
* データベースからのデータ取得は、ディスクファイルからの読み取りに比べて低速です。ODBC ソースからデータを読み込むデータセットは、Sensor や他のディスクファイルのデータから構築される同じサイズのデータセットと比べて、処理（特に再処理時）に時間がかかります。

データの再処理について詳しくは、 [再処理と再変換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

**InsightサーバーをODBC用に設定するには[!DNL event data]**

SQL データベースからデータを読み込むように Data Workbench サーバーを設定するにはまず、次の作業を順に実行する必要があります。

1. データセットを処理する Data Workbench サーバーコンピューターに適切なデータベースクライアントソフトウェア（ODBC ドライバーを含む）をインストールします。

   >[!NOTE]
   >
   >Data Workbenchサーバークラスターで処理するODBCイベントデータを読み込む場合は、クラスター内のすべての処理サーバーにデータベースクライアントソフトウェアをインストールする必要があります。 クラスター内の処理サーバーを指定する方法について詳しくは、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

1. Windows の ODBC データソースアドミニストレーターを使用してデータソースを設定します。

   Data Workbench サーバー（InsightServer64.exe）は、Windows サービスとして実行されることに注意してください。したがって、Data Workbench サーバーがデータソースを使用するためには、通常そのデータセットが、「ユーザー DSN」ではなく「システム DSN」として設定されている必要があります。この設定作業について詳しくは、データベースソフトウェアのドキュメントを参照してください。

適切なData Workbenchサーバーマシンにデータベースクライアントソフトウェアをインストールした後、目的のプロファイルの[!DNL Log Processing]設定ファイル内の適切なパラメーターを編集して、ODBCデータソースを使用するようにデータセットを設定できます。

## パラメーター {#section-15c0218d93364693a565f2609a12f73e}

ODBC（Open Database Connectivity）標準に準拠したデータベースからのデータには、以下のパラメーターがあります。

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> ODBC ソースを識別する情報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Source Name </td> 
   <td colname="col2"> データの読み込み元のデータベースを指定する DSN。DSN は、データセットの処理が実行される Data Workbench サーバーコンピューターの管理者に支給を依頼してください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database Password </td> 
   <td colname="col2"> データベースへの接続に使用するパスワード。<span class="wintitle">データソースアドミニストレーター</span>で DSN のパスワードが設定済みである場合は空欄でも構いません。ここに指定したパスワードは、<span class="wintitle">データソースアドミニストレーター</span>で設定されている DSN のパスワードよりも優先されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Database User ID </td> 
   <td colname="col2"> データベースへの接続に使用するユーザー ID。<span class="wintitle">データソースアドミニストレーター</span>で DSN のユーザー ID が設定済みである場合は空欄でも構いません。ここに指定したユーザー ID は、<span class="wintitle">データソースアドミニストレーター</span>で設定されている DSN のユーザー ID よりも優先されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fields </td> 
   <td colname="col2"> データベース内のデータ列から Data Workbench サーバーの実行エンジンにおけるデータフィールドへのマッピングを指定する列オブジェクトのベクトル。列ごとに、<span class="wintitle">Column Name</span> と <span class="wintitle">Field Name</span> を指定します。<span class="wintitle">Column Name</span> は、SQL の列式です。上記の <span class="wintitle">Table Identifier</span> で識別されるテーブルのコンテキストで有効な列式であることが必要です。列名のほか、SQL 式（テーブル内の列をいくつでも使用可）を指定できます。有効桁数を損なわずに特定のデータ型の値を文字列に変換するために書式設定関数が必要となる場合があります。すべてのデータは、データベースのデフォルトの書式設定メソッドを使って暗黙的に文字列に変換されます。明示的な書式設定式を使用しないと、一部の列のデータ型（date/time データ型など）でデータの損失が生じる可能性があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Increasing ID Column </td> 
   <td colname="col2"> <p>新しい行が追加されたときにインクリメントする（少なくとも減少しない）という基準を満たした列名または SQL 列式。つまり、B という行が A という行よりも後にテーブルに追加された場合、B 行におけるこの列（または列式）の値は、A 行における対応する値よりも（データベースのネイティブのソート順において）大きくなければなりません。 </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> <span class="wintitle">Increasing ID Column</span> には既存の列と同じ名前を使用できますが、必ずしも同じ名前である必要はありません。 </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> この式の型は、SQL の文字データ型であると見なされます。インクリメントする実際の ID 列がそれ以外のデータ型である場合は、列式を指定して文字列に変換する必要があります。通常、比較は辞書式順序（文字単位）で行われるので、値の書式は注意深く設定することが大切です。 </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> この式は SQL ORDER BY 句で使用され、SQL WHERE 句の中で比較されます。実際に使用する列式にインデックスを構築することがきわめて重要となります。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID </td> 
   <td colname="col2"> <p>このパラメーターには、任意の文字列を値として指定できます。このパラメーターの値が指定されていると、異なるログソースからのログエントリを区別して、ログの生成元を特定したり、処理の対象を絞り込んだりすることができます。x-log-source-id フィールドには、ログソースを識別する値がログエントリごとに格納されます。例えば、ODBCSource01 という ODBC ソースからのログエントリを識別したい場合、「<span class="filepath">from ODBCSource01</span>」と入力すれば、このソースから収集されるすべてのログエントリの x-log-source-id フィールドにその文字列が渡されます。 </p> <p> x-log-source-id フィールドについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> イベントデータレコードフィールド</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Run On Server </td> 
   <td colname="col2"> データベースに ODBC クエリーを実行してデータを取得する処理サーバーの <span class="filepath">profile.cfg</span> ファイル内のインデックス値（データセットのすべての処理サーバーは、<span class="filepath">profile.cfg</span> ファイルの Processing Servers パラメーターにリストされ、0 から始まるインデックス値がその各サーバーに割り当てられます）。デフォルト値は 0 です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Table Identifier </td> 
   <td colname="col2"> 読み込むデータが格納されているテーブルまたはビューを指定する SQL 式。標準的なテーブル ID の形式は SCHEMA.TABLE です。 </td> 
  </tr> 
 </tbody> 
</table>

ここに示したのは、Data Workbench の [!DNL Log Processing] 設定ウィンドウで ODBC データソースを指定する例です。このデータソースは、[!DNL Data Source Name] &quot;VSTestO&quot;を持つデータベース内の[!DNL VISUAL.VSL]というテーブルからデータを取得します。 5 つの列オブジェクト（[!DNL Fields]）によって、データベースのデータ列から Data Workbench サーバーにデータをマッピングしています。

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
