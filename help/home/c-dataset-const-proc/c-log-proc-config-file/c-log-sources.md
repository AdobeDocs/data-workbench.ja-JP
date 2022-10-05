---
description: ログソースは、データセット構築用の元データを含むファイルです。
title: ログソース
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 84%

---

# ログソース{#log-sources}

{{eol}}

ログソースは、データセット構築用の元データを含むファイルです。

各データレコードが 1 件のトランザクションレコードまたは 1 回のイベントの発生を表していることから、ログソース内のデータは「イベントデータ」と呼ばれます。Data Workbench サーバーは、 [!DNL Sensors] または他のデータソースから抽出されたもの。

* **収集されたデータ [!DNL Sensors]:**が収集したデータ [!DNL Sensors] HTTP およびアプリケーションサーバーから data workbench サーバーに送信され、高圧縮ログ ( [!DNL .vsl]) ファイルに書き込むことができます。 詳しくは、 [Sensor ファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Insight サーバーによって抽出されたデータ：** Data Workbench サーバーは、フラットファイルや XML ファイル、ODBC 準拠のデータベースからイベントデータを読み取り、デコーダーを使用して、データから目的のエレメントを抽出します。そうしたイベントデータは、メモリに常駐している必要はありませんが、イベントデータを含んでいるレコードには追跡 ID が格納されている必要があります。詳しくは、 [ログファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [XML ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)、および [ODBC データソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**ログソースを追加するには**

1. 開く [!DNL Log Processing.cfg] （data workbench の）
1. 右クリック **[!UICONTROL Log Sources]**&#x200B;を選択し、「 **[!UICONTROL Add New]**.

1. 次のいずれかを選択します。

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. データセットの定義で実際に使用するパラメーターは、データセットの設定プロセスで使用するログソースのタイプによって異なります。ログソースごとの節で紹介しているパラメーターを指定してください。

   * [Sensor ファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [ログファイル](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC データソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. [!DNL Log Processing.cfg] ファイルでログソースを定義し、他のパラメーターに必要な変更を加えたら、そのファイルをローカルに保存してから、Data Workbench サーバー上のデータセットプロファイルに保存します。

   >[!NOTE]
   >
   >Data Workbench サーバー [!DNL File Server Unit] を受け取り、保管できる [!DNL Sensor] ファイル、ログファイル、XML ファイルを使用して、Data Workbench サーバーの [!DNL Data Processing Units] データセットを構築する 詳しくは、 [Insight サーバーのファイルサーバーユニットの設定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   ログソースの設定は、 [!DNL Transformation Dependency Map]. 詳しくは、 [!DNL Transformation Dependency Map]を参照してください。 [データセット設定ツール](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## 要件 {#section-d5901a4872774ad5bd01a18db114f1f2}

が収集したイベントデータ [!DNL Sensors] HTTP およびアプリケーションサーバーから data workbench サーバーに送信され、高圧縮ログ ( [!DNL .vsl]) ファイルに書き込むことができます。 この [!DNL .vsl] ファイル形式は data workbench サーバーによって管理され、各ファイルには次の形式の名前が付けられます。

YYYYMMDD-*SENSORID*.VSL

YYYYMMDD はファイルの日付で、*SENSORID* は、データを収集して Data Workbench サーバーに送信した [!DNL Sensor] の名前（カンパニー内で割り当てられる名前）です。

## パラメーター {#section-5c3f1e341c284486aeba3452057da7f3}

[!DNL Sensor] のファイルには、以下のパラメーターを使用できます。

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Log Paths </td> 
   <td colname="col2"> <p><span class="filepath">.vsl</span> ファイルが格納されるディレクトリ。デフォルトでは Logs ディレクトリです。Data Workbench サーバーのインストールディレクトリが相対パスの基準となります。 </p> <p>処理対象とする <span class="filepath">.vsl</span> ファイルは、ワイルドカード文字で指定できます。 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> 「*」は、任意の数の文字と一致します。 </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> 「?」は、単一の文字と一致します。 </li> 
     </ul> </p> <p> 例えば、<span class="filepath">Logs\*.vsl</span> というパスは、Logs ディレクトリ内の、<span class="filepath">.vsl</span> で終わるすべてのファイルと一致します。<span class="filepath">Logs\*-SENSOR?.vsl</span> というパスは、任意の日付（YYYYMMDD）を持ち、SENSOR の後に 1 文字続く（SENSOR1 など）、Logs ディレクトリ内のファイルと一致します。 </p> <p> 指定したパスのすべてのサブディレクトリを検索対象にしたい場合は、Recursive パラメーターを true に設定する必要があります。 </p> <p> <p>注意：Data Workbench サーバーの<span class="wintitle">ファイルサーバーユニット</span>からファイルを読み取る場合、適切な URI を Log Paths パラメーターに入力する必要があります。例えば、<span class="filepath">/Logs/*-*.vsl</span> という URI は、Logs ディレクトリ内のすべての <span class="filepath">.vsl</span> ファイルと一致します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Server </td> 
   <td colname="col2">ファイルサーバーへの接続に必要な情報（アドレス、名前、ポートなど）。Log Server パラメーターに値が入力されている場合、<span class="wintitle">Log Paths</span> は URI として解釈されます。それ以外の場合は、ローカルパスとして解釈されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Source ID </td> 
   <td colname="col2"> <p>このパラメーターには、任意の文字列を値として指定できます。このパラメーターの値が指定されていると、異なるログソースからのログエントリを区別して、ログの生成元を特定したり、処理の対象を絞り込んだりすることができます。x-log-source-id フィールドには、ログソースを識別する値がログエントリごとに格納されます。例えば、VSensor01 という <span class="wintitle">Sensor</span> からのログエントリを識別したい場合、「<span class="filepath">from VSensor01</span>」と入力すれば、このソースから収集されるすべてのログエントリの x-log-source-id フィールドにその文字列が渡されます。 </p> <p> x-log-source-id フィールドについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> イベントデータレコードフィールド</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recursive </td> 
   <td colname="col2"> true または false。true に設定した場合、<span class="wintitle">Log Paths</span> に指定された各パスのすべてのサブディレクトリを対象に、指定したファイル名やワイルドカードパターンと一致するファイルが検索されます。デフォルト値は false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use Start/End Times </td> 
   <td colname="col2"> <p>true または false。このパラメーターを true に設定し、Start Time または End Time を指定する場合、ログソースのすべてのファイルの名前は、ISO 形式の日付（YYYYMMDD）で始まっている必要があります。すべてのファイルに、GMT に基づく 1 日分（特定の日付の 0000 GMT から翌日の 0000 GMT までなど）のデータが含まれていることが前提となります。GMT の 1 日に対応しないデータがログソースファイルに含まれている場合、結果が不正確になるので、それを避けるために、このパラメーターを false に設定する必要があります。 </p> <p> <p>注意：<span class="filepath">Sensor</span> によって収集されたデータの <span class="wintitle">.vsl</span> ファイルは、特に何もしなくても、名前付けと時間範囲に関する前述の要件を自動的に満たします。このパラメーターが true に設定されている場合、Data Workbench サーバーは常に、指定された Start Time と End Time の期間に該当する ISO 形式の日付を名前に含んだファイルからのデータを処理します。このパラメーターが false に設定されている場合、Data Workbench サーバーは、ログ処理の過程ですべての <span class="filepath">.vsl</span> ファイルを読み取り、Start Time から End Time までの期間に該当するデータが含まれているファイルを特定します。 </p> </p> <p> Start Time パラメーターと End Time パラメーターについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> データフィルター</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>次の設定パラメーターは使用しないでください。 [!DNL Sensor] データソースを使用して、データセットに含めるログファイル内のログエントリを決定します。 その場合は、特定のディレクトリ内のすべてのログファイルを指すようにデータソースを設定したうえで、[!DNL Log Processing.cfg] の Start Time パラメーターと End Time パラメーターを使用し、データセットの構築に使用するログエントリを選択します。詳しくは、 [データフィルター](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

イベントデータを含むファイルは、次の要件を満たしている必要があります。

* ファイル内のイベントデータレコードは、1 件につき 1 行で記述されている必要があります。
* レコード内のフィールドは、データが存在するかどうかに関係なく、ASCII の区切り文字で区切られている必要があります。Data Workbench サーバーの要件として定められた区切り文字はありません。行終端文字以外で、かつイベントデータ自体に出現していない文字であれば、どのような文字でも使用できます。
* ファイル内の各レコードには次のデータが含まれている必要があります。

   * 追跡 ID
   * タイムスタンプ

* データ処理の始まりと終わりの時間を指定するために、各ファイル名は次の形式になっている必要があります。

   * [!DNL YYYYMMDD-SOURCE.log]

   *YYYYMMDD* はファイル内の全データのグリニッジ標準時（GMT）の日付で、*SOURCE* はファイルに含まれているデータの取得元を表す変数です。

   >[!NOTE]
   >
   >データセットへの組み込みを計画しているログファイルの確認については、Adobeコンサルティングサービスにお問い合わせください。

## パラメーター {#section-83a861ac24954d54bbb9530e4d8bf23c}

ログファイルのログソースに関して、以下の表に示したパラメーターが用意されています。

>[!NOTE]
>
>ログファイルログソースを処理するには、 [!DNL Log Processing Dataset Include] ファイル。 [!DNL Log Processing.cfg] ファイルに加えて、ログファイルからデータを抽出するデコーダーを定義するための特別なパラメーターを含めます。 ログファイルログソースのデコーダーの定義について詳しくは、 [テキストファイルデコーダーグループ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> ログファイルソースを識別する情報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログパス </td> 
   <td colname="col2"> <p>ログファイルを格納するディレクトリ。デフォルトでは Logs ディレクトリです。Data Workbench サーバーのインストールディレクトリが相対パスの基準となります。 </p> <p> 処理対象とするログファイルは、ワイルドカード文字で指定できます。 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> 「*」は、任意の数の文字を表します。 </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> 「?」は、単一の文字を表します。 </li> 
     </ul> </p> <p> 例えば、<span class="filepath">Logs\*.log</span> というパスは、Logs ディレクトリ内の、<span class="filepath">.log</span> で終わるすべてのファイルと一致します。 </p> <p> 指定したパスのすべてのサブディレクトリを検索対象にしたい場合は、Recursive パラメーターを true に設定する必要があります。 </p> <p> Data Workbench サーバーの<span class="wintitle">ファイルサーバーユニット</span>からファイルを読み取る場合、適切な URI を Log Paths パラメーターに入力する必要があります。例えば、<span class="filepath">URI/Logs/*.log</span> は、Logs ディレクトリ内のすべての <span class="filepath">.log</span> ファイルと一致します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログサーバー </td> 
   <td colname="col2"> ファイルサーバーへの接続に必要な情報（アドレス、名前、ポートなど）。Log Server パラメーターに値が入力されている場合、<span class="wintitle">Log Paths</span> は URI として解釈されます。それ以外の場合は、ローカルパスとして解釈されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressed </td> 
   <td colname="col2"> true または false。Data Workbench サーバーによって読み取られるログファイルが圧縮 gzip ファイルである場合、この値を true に設定する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Decoder Group </td> 
   <td colname="col2"> ログファイルログソースに適用するテキストファイルデコーダーグループの名前。この名前は、<span class="wintitle">ログ処理データセットインクルード</span>ファイルに指定された、対応するテキストファイルデコーダーグループの名前と完全に一致している必要があります。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> テキストファイルデコーダーグループ</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログソース ID </td> 
   <td colname="col2"> <p>このパラメーターには、任意の文字列を値として指定できます。このパラメーターの値が指定されていると、異なるログソースからのログエントリを区別して、ログの生成元を特定したり、処理の対象を絞り込んだりすることができます。x-log-source-id フィールドには、ログソースを識別する値がログエントリごとに格納されます。例えば、LogFile01 というログファイルソースからのログエントリを識別したい場合、「<span class="filepath">from LogFile01</span>」と入力すれば、このソースから収集されるすべてのログエントリの x-log-source-id フィールドにその文字列が渡されます。 </p> <p> x-log-source-id フィールドについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> イベントデータレコードフィールド</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mask Pattern </td> 
   <td colname="col2"> <p>規則的な名前のログファイルを指定するための正規表現パターン。一連のログファイルのソースを識別する目的で使用されます。考慮されるのはファイル名のみです。パスと拡張子は、正規表現のマッチングの対象外となります。<span class="wintitle">マスクパターン</span>を指定しなかった場合は、マスクが自動的に生成されます。 </p> <p> <span class="filepath">Logs\010105server1.log</span> や <span class="filepath">Logs\010105server2.log</span> というファイルの場合、<span class="wintitle">マスクパターン</span>は <code>[0-9]{6}(.*)</code>. このパターンを適用した場合、ファイル名から「server1」や「server2」という文字列が抽出されます。 </p> <p> 詳しくは、 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 正規表現</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 再帰 </td> 
   <td colname="col2"> true または false。このパラメーターを true に設定した場合、<span class="wintitle">Log Paths</span> に指定された各パスのすべてのサブディレクトリを対象に、指定したファイル名やワイルドカードパターンと一致するファイルが検索されます。デフォルト値は false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reject File </td> 
   <td colname="col2"> デコーダーの条件を満たさないログエントリを含むファイルのパスと名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始/終了時間を使用 </td> 
   <td colname="col2"> <p>true または false。このパラメーターを true に設定し、Start Time または End Time を指定する場合、ログソースのすべてのファイルの名前は、ISO 形式の日付（YYYYMMDD）で始まっている必要があります。すべてのファイルに、GMT に基づく 1 日分（特定の日付の 0000 GMT から翌日の 0000 GMT までなど）のデータが含まれていることが前提となります。ログソースファイル名の先頭が ISO 形式の日付になっていない場合や、GMT の 1 日に対応しないデータがファイルに含まれている場合、結果が不正確になるので、それを避けるために、このパラメーターを false に設定する必要があります。 </p> <p> <p>注意：前述の命名規則と時間範囲の要件をログファイルが満たしている場合、このパラメーターを true に設定することによって、指定したテキストファイルデコーダーグループによって読み取り対象のファイルが限定され、ISO 形式の日付をファイル名に含んでいて、Start Time と End Time で指定した期間に該当するファイルだけが読み取り対象となります。このパラメーターが false に設定されている場合、Data Workbench サーバーは、ログ処理の過程ですべてのログファイルを読み取り、Start Time から End Time までの期間に該当するデータが含まれているファイルを特定します。 </p> </p> <p> Start Time パラメーターと End Time パラメーターについて詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">データフィルター</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

次の例では、2 種類のログソースからデータセットが構築されます。

Log Source 0 には、[!DNL Sensor] によって収集されたイベントデータから生成されたログファイルが指定されています。このデータソースは、Logs というディレクトリと、そのディレクトリ内のすべてのファイルを、 [!DNL .vsl] ファイル名の拡張子。

Log Source 1 は、Logs ディレクトリ内のすべてのファイルを [!DNL .txt] ファイル名の拡張子。 このログソースのデコーダーグループには、「Text Logs」という名前が付けられています。

![](assets/cfg_LogProcessing_LogSources.png)

データセットのデータソースを定義した後でログファイルを削除したり移動したりすることは避けてください。データソースのディレクトリには、新しく作成されたログファイルだけを追加する必要があります。

<!--
c_xml_log_sources.xml
-->

イベントデータを含むファイルは、次の要件を満たしている必要があります。

* イベントデータは、必要な親子関係を持った適切な形式の XML ファイルに格納されていなければなりません。
* XML ファイル形式ごとに一意のデコーダーグループが存在している必要があります。デコーダーグループの作成について詳しくは、 [XML デコーダーグループ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* ファイル内の訪問者レコードにはそれぞれ次のデータが含まれている必要があります。

   * 追跡 ID
   * タイムスタンプ

* データ処理の始まりと終わりの時間を指定するために、各ファイル名は次の形式になっている必要があります。

[!DNL YYYYMMDD-SOURCE.log]

*YYYYMMDD* はファイル内の全データのグリニッジ標準時（GMT）の日付で、*SOURCE* はファイルに含まれているデータの取得元を表す変数です。

これらの要件を満たした XML ファイルの例については、 [XML デコーダーグループ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>データセットへの組み込みを計画している XML ログファイルの確認については、Adobeコンサルティングサービスにお問い合わせください。

## パラメーター {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

XML ログソースに関して、以下の表に示したパラメーターが用意されています。

>[!NOTE]
>
>XML ログソースを処理するには、 [!DNL Log Processing Dataset Include] ファイル。 [!DNL Log Processing.cfg] ファイルに加えて、XML ファイルからデータを抽出するデコーダーを定義するための特別なパラメーターを含めます。 XML ログソースに対するデコーダーの定義について詳しくは、 [XML デコーダーグループ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名前 </td> 
   <td colname="col2"> XML ログソースを識別する情報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログパス </td> 
   <td colname="col2"> <p>XML ログソースが格納されるディレクトリ。デフォルトでは Logs ディレクトリです。Data Workbench サーバーのインストールディレクトリが相対パスの基準となります。 </p> <p> 処理対象とする XML ログソースは、ワイルドカード文字で指定できます。 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> 「*」は、任意の数の文字と一致します。 </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> 「?」は、単一の文字と一致します。 </li> 
     </ul> </p> <p>例えば、<span class="filepath">Logs\*.xml</span> というパスは、Logs ディレクトリ内の、<span class="filepath">.xml</span> で終わるすべてのファイルと一致します。 </p> <p> 指定したパスのすべてのサブディレクトリを検索対象にしたい場合は、<span class="wintitle">Recursive</span> フィールドを true に設定する必要があります。 </p> <p> <p>注意：Data Workbench サーバーの<span class="wintitle">ファイルサーバーユニット</span>からファイルを読み取る場合、適切な URI を <span class="wintitle">Log Paths</span> フィールドに入力する必要があります。例えば、<span class="filepath">URI/Logs/*.xml</span> は、Logs ディレクトリ内のすべての <span class="filepath">.xml</span> ファイルと一致します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログサーバー </td> 
   <td colname="col2"> ファイルサーバーへの接続に必要な情報（アドレス、名前、ポートなど）。<span class="wintitle">Log Server</span> フィールドに値が入力されている場合、<span class="wintitle">Log Paths</span> は URI として解釈されます。それ以外の場合は、ローカルパスとして解釈されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Insight サーバーのファイルサーバーユニットの設定</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 圧縮 </td> 
   <td colname="col2"> true または false。Data Workbench サーバーによって読み取られる XML ログソースが圧縮 gzip ファイルである場合、この値を true に設定する必要があります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> デコーダーグループ </td> 
   <td colname="col2"> XML ログソースに適用する XML デコーダーグループの名前。この名前は、<span class="wintitle">ログ処理データセットインクルード</span>ファイルに指定された、対応する XML デコーダーグループの名前と完全に一致している必要があります。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML デコーダーグループ</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ログソース ID </td> 
   <td colname="col2"> <p>このフィールドには、任意の文字列を値として指定できます。このフィールドの値が指定されていると、異なるログソースからのログエントリを区別して、ログの生成元を特定したり、処理の対象を絞り込んだりすることができます。x-log-source-id フィールドには、ログソースを識別する値がログエントリごとに格納されます。例えば、XMLFile01 というログファイルソースからのログエントリを識別したい場合、「<span class="filepath">from XMLFile01</span>」と入力すれば、このソースから収集されるすべてのログエントリの x-log-source-id フィールドにその文字列が渡されます。 </p> <p> x-log-source-id フィールドについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> イベントデータレコードフィールド</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> マスクパターン </td> 
   <td colname="col2"> <p>規則的な名前のログファイルを指定するための正規表現パターン。一連のログファイルのソースを識別する目的で使用されます。考慮されるのはファイル名のみです。パスと拡張子は、正規表現のマッチングの対象外となります。<span class="wintitle">マスクパターン</span>を指定しなかった場合は、マスクが自動的に生成されます。 </p> <p> <span class="filepath">Logs\010105server1.xml</span> や <span class="filepath">Logs\010105server2.xml</span> というファイルの場合、マスクパターンは <code>[0-9]{6}(.*)</code>. このパターンを適用した場合、ファイル名から「server1」や「server2」という文字列が抽出されます。 </p> <p> 詳しくは、 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 正規表現</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 再帰 </td> 
   <td colname="col2"> true または false。このパラメーターを true に設定した場合、<span class="wintitle">Log Paths</span> に指定された各パスのすべてのサブディレクトリを対象に、指定したファイル名やワイルドカードパターンと一致するファイルが検索されます。デフォルト値は false です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ファイルを拒否 </td> 
   <td colname="col2"> デコーダーの条件を満たさないログエントリを含むファイルのパスと名前。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始/終了時間を使用 </td> 
   <td colname="col2"> <p>true または false。このパラメーターを true に設定し、Start Time または End Time を指定する場合、ログソースのすべてのファイルの名前は、ISO 形式の日付（YYYYMMDD）で始まっている必要があります。すべてのファイルに、GMT に基づく 1 日分（特定の日付の 0000 GMT から翌日の 0000 GMT までなど）のデータが含まれていることが前提となります。ログソースファイル名の先頭が ISO 形式の日付になっていない場合や、GMT の 1 日に対応しないデータがファイルに含まれている場合、結果が不正確になるので、それを避けるために、このパラメーターを false に設定する必要があります。 </p> <p> <p>注意：前述の命名規則と時間範囲の要件を XML ファイルが満たしている場合、このパラメーターを true に設定することによって、指定した XML デコーダーグループによって読み取り対象のファイルが限定され、ISO 形式の日付をファイル名に含んでいて、Start Time と End Time で指定した期間に該当するファイルだけが読み取り対象となります。このパラメーターが false に設定されている場合、Data Workbench サーバーは、ログ処理の過程ですべての XML ファイルを読み取り、Start Time から End Time までの期間に該当するデータが含まれているファイルを特定します。 </p> </p> <p> Start Time パラメーターと End Time パラメーターについて詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">データフィルター</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>データセットのデータソースを定義した後で XML ログソースを削除したり移動したりしないでください。 データソースのディレクトリには、新しく作成された XML ファイルだけを追加する必要があります。

<!--
AVRO-log-file.xml
-->

Avro データフィードは、より効率的な方法でデータを Data Workbench に統合します。

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro は、トラフィックおよびコマースデータ用の単一ソース形式を提供します。
* Avro フィードは、1 日ごとに提供される複数のソースチャンクの圧縮データです。入力されたフィールドのみをプロビジョニングしたり、監視および通知機能を提供したり、履歴データにアクセスしたり、自動リカバリしたりします。
* スキーマ（AVRO ログファイルの自動定義レイアウト）は、各ファイルの最初に含まれます。
* デコーダーへの変更なしに Data Workbench データを取り込むための情報をサポートする新しいフィールドが追加されます。これには、以下が含まれます。

   * eVar：1 ～ 250（以前は 1 ～ 75）
   * カスタムイベント：1 ～ 1000（1 ～ 100 に対して）
   * モバイル、ソーシャル、ビデオデータ用のソリューション変数へのアクセス

>[!NOTE]
>
>また、Avro フィードを使用すると、シャットダウンせずにフィード内の新しいフィールドに即座にアクセスでき、サービス時間の要件なしにフィールドを更新できます。

Avro データフィードは、個別のファイルに設定されます。

* **AVRO ログファイル**：これは、トラフィックおよびコマースデータをフォーマットするためにデコーダーから生成された Avro ログ形式です。
* **AVRO デコーダーファイル**：このファイルを使用すると、値を新しい Avro 形式にマッピングできます。AVRO デコーダーウィザードを使用して、デコーダーを設定できます。

## AVRO デコーダーウィザード {#section-9a824b4c3d5549e7952a7111232035b2}

このウィザードは、Avro デコーダーログファイルを設定します。

開くには、ワークスペースで右クリックして、**管理者**／**ウィザード**／**AVRO デコーダーウィザード**&#x200B;を選択します。

**手順 1：****AVRO ログファイルを選択**&#x200B;します。

この手順では、Avro スキーマのソースファイルを選択できます。スキーマは、ログファイル（.log）または既存のデコーダーファイル（.avro）からアクセスできます。スキーマは、どちらかのファイルから取り込むことができます。

| **Avro ログファイル** | クリックして（.log）ファイルを開くと、ログファイルの最上部にスキーマが表示され、デコーダーファイルを生成します。 |
|---|---|
| **AVRO デコーダーファイル** | クリックして開き、既存のデコーダー（.avro）ファイルのスキーマを編集します。 |

**手順 2：入力フィールドを選択**&#x200B;します。

ログ処理を経るために、データセットで使用する入力フィールドを選択します。ファイルのすべてのフィールドが表示され、フィード用のフィールドを選択できます。

>[!NOTE]
>
>A [!DNL x-product(Generates row)] フィールドは、データ内で配列が見つかった場合に提供されます。 このフィールドは、配列にネストされたデータ用に新しい行を入力フィールドとして生成します。例えば、配列に多くの製品の値を持つヒット行がある場合、各製品の入力ファイルに行が生成されます。

| **デフォルトを選択** | デフォルトフィールドの標準として識別するためのフィールドを選択します。 |
|---|---|
| **すべて選択** | ファイルのすべてのフィールドを選択します。 |
| **すべて選択解除** | ファイルのすべてのフィールドをクリアします。 |

**手順3：行を生成するためにコピーされるフィールドを選択します。**

新しい行は配列のネストされた値から作成できるので、それぞれの作成された新しい行には、追跡 ID およびタイムスタンプがある必要があります。この手順により、追跡 ID およびタイムスタンプなどの親レコードから行にコピーされるフィールドを選択できます。また、各行に追加したい他の値も選択できます。

| **デフォルトを選択** | 追跡 ID およびタイムスタンプなど、各行に追加された新しい列の値に必要なデフォルトフィールドの標準セットを選択します。例えば、[!DNL hit_source] フィールドは、それぞれの新しい行に追加されるために必要なデフォルト値です（リストのデフォルト値として定義されます）。必要に応じて、他の列の値を各行に追加できます。 |
|---|---|
| **すべて選択** | ファイルのすべてのフィールドを選択します。 |
| **すべて選択解除** | ファイルのすべてのフィールドをクリアします。 |

**検索**&#x200B;ボックスを使用して、リストの値を検索します。

**手順 4：デコーダー名を指定します。**

フィールドのグループに名前を割り当てて、デコーダーファイルとして保存します。名前は、ログソースで指定したデコーダーグループ名と一致する必要があります。

**手順 5：デコーダーファイルを保存します。**

ファイルメニューが開き、デコーダーファイルに名前を付けてとして保存されます。 [!DNL .cfg] ファイルを **ログ** フォルダー。
