---
description: データセットプロファイルの Log Processing.cfg ファイルを編集するための手順について説明します。
solution: Analytics
title: ログ処理設定ファイルの編集
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ログ処理設定ファイルの編集{#editing-the-log-processing-configuration-file}

データセットプロファイルの Log Processing.cfg ファイルを編集するための手順について説明します。

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

   >[!NOTE]
   >
   >Datasetディレクトリ内には、Log Processingサブディレクトリが存在する場合があります。 This subdirectory contains the [!DNL Log Processing Dataset Include] files that have been created for one or more inherited profiles. データセット [インクルードファイルを参照](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. の横のチェックマークを右クリックし、をク [!DNL Log Processing.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Workstation]**&#x200B;す。 The [!DNL Log Processing.cfg] window appears.

   また、からファイルを開 [!DNL Log Processing.cfg] くこともできま [!DNL Transformation Dependency Map]す。 変換依存関係マップについて詳しくは、「データセット設定ツ [ール」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)い。

1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   Data Workbench ウィンドウ内で [!DNL Log Processing.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。You can also use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

   >[!NOTE]
   >
   >A [!DNL Log Processing Dataset Include] file for an inherited profile contains a subset of the parameters described in the following table as well as some additional parameters. データセット [インクルードファイルを参照](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> 説明 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Log Sources </td> 
      <td colname="col2"> データのソース。Log Sourcesを参 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 照してくださ </a>い。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> End Time </td> 
      <td colname="col2"> <p>(オプション)データのフィルター。タイムスタンプがこの時刻より前（この時刻は含まず）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">January 1 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p>例えば、July 29 2013 00:00:00 EDT を End Time として指定した場合、米国東部夏時間の 2013 年 7 月 28 日 11:59:59 PM までのデータが対象となります。詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">データフィルター</a>を参照してください。 </p> <p>タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">タイムゾーンのコード</a>を参照してください。 </p> <p> <p>注意：<span class="wintitle">Sensor</span>、ログファイル、XML ソースのパラメーターである Use Start/End Times は、このパラメーターと連動します。これらのソースの種類について <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> は、ログソ </a> ースの節を参照してください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fields </td> 
      <td colname="col2"> (オプション)<span class="wintitle">Fields</span> は、<span class="wintitle">ログ処理データセットインクルード</span>ファイルに定義することをお勧めします。Log Processing Dataset Include Files <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> を参照してくださ </a>い。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Group Maximum Key Bytes </td> 
      <td colname="col2"> <p>サーバーが 1 つの追跡 ID で処理できるイベントデータの最大量。この制限を超えるデータは、データセット構築プロセスから除外されます。キー分割が有効である場合は 2e6 に、そうでない場合は 1e6 に設定する必要があります。詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">キー分割</a>を参照してください。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold </td> 
      <td colname="col2"> <p>(オプション)より小さな標本（データセットの行）をランダムに抽出するためのサンプリング係数。数値 n に設定した場合、n 件の追跡 ID につき 1 件のみがデータセットを入力するので、データセットの合計行数を 1/n に減らすことができます。 </p> <p>100％の精度を必要とするデータセットを作成するには（つまり、すべての行を含めるには）、Hash Threshold を 1 に設定します。 </p> <p>値： </p> <span class="filepath">Hash Threshold = 1</span>（すべての行を含む 100％のデータ。） <p> <span class="filepath">Hash Threshold = 2</span>（1/2 のデータで、半分の行を含みます。） </p> <p> <span class="filepath">Hash Threshold = 3 </span>（1/3 のデータで、3 行に 1 行を含みますが、クエリー完了で 34％に四捨五入します。） </p> <p> <span class="filepath">Hash Threshold = 4 </span>（1/4 のデータで、4 行に 1 行を含みます。） </p> <p> </p> <p> <p>注意：<span class="filepath">Hash Threshold = 8</span> を使用すると、1/8 のデータ（つまり、12.5％）になります。ただし、この値について、四捨五入した<span class="uicontrol">クエリー完了</span>の値は 13％になります。同様の例として、<span class="filepath">Hash Threshold = 6</span> は 17％のクエリー解決になります。<span class="filepath">Hash Threshold = 13</span> は 8％のクエリー解決になります。 </p> </p> <p><span class="filepath">Log Processing.cfg</span> ファイルと <span class="filepath">Transformation.cfg</span> ファイルの両方に <span class="wintitle">Hash Threshold</span> を指定した場合、それぞれの値が順に適用されるのではなく、いずれか大きい方の値だけが適用されます。データフィル <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> ターを参照してくだ </a>さい。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition </td> 
      <td colname="col2"> (オプション)データセットにログエントリを含めるかどうかの判断基準となるルールを定義します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> ログ記録条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess </td> 
      <td colname="col2"> <p>(オプション)ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えて Data Workbench サーバーコンピューターにファイルを保存すると、データの再処理が開始されます。 </p> <p>詳しくは、<a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">再処理と再変換</a>を参照してください。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space </td> 
      <td colname="col2"> <p>キーの分割に関係するパラメーター。キー分割が有効である場合、この値を 6e6 に設定する必要があります。詳しくは、<a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split">キー分割</a>を参照してください。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bytes </td> 
      <td colname="col2"> <p>キーの分割に関係するパラメーター。キー分割が有効である場合は 1e6 に、そうでない場合は 0 に設定する必要があります。詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">キー分割</a>を参照してください。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Space Ratio </td> 
      <td colname="col2"> <p>キーの分割に関係するパラメーター。キー分割が有効である場合、この値を 10 に設定する必要があります。詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">キー分割</a>を参照してください。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages </td> 
      <td colname="col2"> <p>(オプション)<span class="wintitle">ログ処理データセットインクルード</span>ファイルで使用できる処理ステージの名前処理ステージにより、<span class="wintitle">ログ処理データセットインクルード</span>ファイル内に定義された変換の順序付けを行うことができます。複数の<span class="wintitle">ログ処理データセットインクルード</span>ファイルに変換を定義してあるとき、ログ処理の決まったポイントで特定の変換を実行したい場合に、このパラメーターが非常に役立ちます。 </p> <p><span class="wintitle">ログ処理データセットインクルード</span>ファイル内の各変換が、ログ処理の過程でどのような順序で実行されるかは、ここにリストしたステージの順序によって決まります。Preprocessing と Postprocessing は、ビルトインのステージです。Preprocessing は常に最初のステージに、Postprocessing は常に最後のステージになります。デフォルトでは、Default という名前のステージが 1 つ存在します。 </p> <p> <b>新しい処理ステージを追加するには</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71"><span class="filepath">Log Processing.cfg</span> ウィンドウで <span class="uicontrol">Stages</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Stage</span> をクリックします。 </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">新しいステージの名前を入力します。 </li> 
      </ul> </p> <p> <b>既存の処理ステージを削除するには</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">削除するステージに対応する番号を右クリックし、「<span class="uicontrol">&lt;</span>#stage_number<i>&gt;<span class="uicontrol"></span> を削除</i>」をクリックします。 </li> 
      </ul> </p> <p> <p>注意：<span class="wintitle">ログ処理データセットインクルード</span>ファイルで <span class="wintitle">Stage</span> を指定するときは、ここに入力したステージの名前と完全に一致させる必要があります。データセットイ <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> ンクルードファイルを参照してく </a>ださい。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time </td> 
      <td colname="col2"> <p>(オプション)データのフィルター。タイムスタンプがこの時刻以後（この時刻を含む）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> January 1 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、「July 29 2013 00:00:00 EDT」を Start Time として指定した場合、米国東部夏時間の 2013 年 7 月 29 日 12:00:00 AM 以降のデータが対象となります。詳しくは、<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">データフィルター</a>を参照してください。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">タイムゾーンのコード</a>を参照してください。 </p> <p> <p>注意：<span class="wintitle">Sensor</span>、ログファイル、XML ソースのパラメーターである Use Start/End Times は、このパラメーターと連動します。これらのソースの種類について <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> は、ログソ </a> ースの節を参照してください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> タイムゾーン </td> 
      <td colname="col2"> <p>(オプション)ログ処理中に時刻の変換（x-local-timestringフィールドで表される変換など）に使用されるData Workbenchサーバーのタイムゾーン。 </p> <p> <p>注意：データセット構築のログ処理段階で、変換済みの時刻フィールドにアクセスしたい場合、Time Zone を指定する必要があります。指定しないと、Data Workbench サーバーによってイベントログにエラーが記録されます。 </p> </p> <p>詳しくは、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> タイムゾーン </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> (オプション)ログ処理における変換は、<span class="wintitle">ログ処理データセットインクルード</span>ファイルに定義することをお勧めします。Log Processing Dataset Include Files <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> を参照してくださ </a>い。 </td> 
   </tr> 
   </tbody> 
   </table>

1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
1. で、列 [!DNL Profile Manager]のチェックマークを右クリ [!DNL Log Processing.cfg]ック [!DNL User] し、 **[!UICONTROL Save to]** / *&lt;**[!UICONTROL dataset profile name]*** >をクリックして、ローカルに適用した変更を有効にします。 データセットプロファイルの同期後、データの再処理が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

   データの再処理について詳しくは、再処理と再変換を [参照してください](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
