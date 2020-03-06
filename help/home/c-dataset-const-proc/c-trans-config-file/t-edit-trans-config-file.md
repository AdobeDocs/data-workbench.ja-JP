---
description: データセットプロファイルの Transformation.cfg ファイルを編集する手順について説明します。
solution: Analytics
title: 変換設定ファイルの編集
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換設定ファイルの編集{#editing-the-transformation-configuration-file}

データセットプロファイルの Transformation.cfg ファイルを編集する手順について説明します。

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

   >[!NOTE]
   >
   >Datasetディレクトリ内には、Transformationサブディレクトリが存在する場合があります。 This subdirectory contains the [!DNL Transformation Dataset Include] files that have been created for one or more inherited profiles. ファイルについて詳しくは、 [!DNL Transformation Dataset Include] 「データセットインクルードフ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。

1. の横のチェックマークを右クリックし、をク [!DNL Transformation.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Workstation]**&#x200B;す。 The [!DNL Transformation.cfg] window appears.

   また、からファイルを開 [!DNL Transformation.cfg] くこともできま [!DNL Transformation Dependency Map]す。 詳しくは、データセッ [!DNL transformation dependency maps]ト設定ツー [ルを参照してください](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   Data Workbench ウィンドウ内で [!DNL Transformation.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] files for an inherited profile contains a subset of the parameters described in the following table as well as some additional parameters. ファイルについて詳しくは、デ [!DNL Transformation Dataset Include] ータセットインクルードフ [ァイルを参照してください。](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> 説明 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> End Time </td> 
      <td colname="col2"> <p>(オプション)データのフィルター。タイムスタンプがこの時刻より前（この時刻は含まず）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、「July 29 2013 00:00:00 EDT」を End Time として指定した場合、米国東部夏時間の 2013 年 7 月 28 日 11:59:59 PM までのデータが対象となります。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">タイムゾーンのコード</a>を参照してください。 </p> <p> <p>注意：End Time の値を指定した場合、End Time という名前のパラメーターが設定され、データセット構築の変換段階全体で適用されます。パラメーターについて詳しくは、「データセットインクルード <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> ファイルでのパラメーターの定義」を参照してくだ </a>さい。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拡張ディメンション </td> 
      <td colname="col2"> (オプション)拡張ディメンションは、<span class="wintitle">変換データセットインクルード</span>ファイルに定義することをお勧めします。詳しくは、変換データセットインクルードフ <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> ァイル（英語のみ）を参照してくだ </a>さい。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold </td> 
      <td colname="col2"> <p>(オプション)より小さな標本（データセットの行）をランダムに抽出するためのサンプリング係数。数値 n に設定した場合、n 件の追跡 ID につき 1 件のみがデータセットに組み入れられ、データセットの合計行数を 1/n に減らすことができます。100％の精度が必要なデータセットを作成する（つまりすべての行を対象とする）には、Hash Threshold を 1 に設定します。 </p> <p> <span class="filepath">Log Processing.cfg</span> ファイルと <span class="filepath">Transformation.cfg</span> ファイルの両方に Hash Threshold を指定した場合、それぞれの値が順に適用されるのではなく、いずれか大きい方の値だけが適用されます。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition </td> 
      <td colname="col2"> (オプション)ログ処理から出力されたログエントリをデータセットプロファイルに含めるかどうかの判断基準となるルールを定義します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> ログ記録条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> New Visitor Condition </td> 
      <td colname="col2"> (オプション)Web データ用。データに訪問者を含めるかどうかの判断基準となるルールを定義します。<span class="wintitle">New Visitor Condition</span> は、特定の訪問者の（時系列順に並んだ）ログのうち、データセットに使用する最初のエントリを定義します。それ以降、この条件を満たしているかどうかに関係なく、同じ訪問者のすべてのログエントリがデータセットに組み入れられます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> 新規訪問者条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess </td> 
      <td colname="col2"> <p>(オプション)ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えてファイルを保存すると、データの再変換が開始されます。 </p> <p> データの再処理について詳しくは、<a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">再処理と再変換</a>を参照してください。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schema Checking </td> 
      <td colname="col2"> true または false。true の場合、データセットの破損の問題を Data Workbench サーバーが特定し、その Trace ディレクトリ内のログファイルに問題に関する情報を記録します。デフォルト値は true です。このパラメーターは常に true にしておくことをお勧めします。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages </td> 
      <td colname="col2"> <p>(オプション)<span class="wintitle">変換データセットインクルード</span>ファイルで使用できる処理ステージの名前。処理ステージにより、<span class="wintitle">変換データセットインクルード</span>ファイル内に定義された変換の順序付けを行うことができます。複数の<span class="wintitle">変換データセットインクルード</span>ファイルに変換を定義してあるとき、変換の決まったポイントで特定の変換を実行したい場合に、このパラメーターが非常に役立ちます。 </p> <p> <span class="wintitle">変換データセットインクルード</span>ファイル内の各変換が、変換の過程でどのような順序で実行されるかは、ここにリストしたステージの順序によって決まります。<span class="wintitle">Preprocessing</span> と <span class="wintitle">Postprocessing</span> はビルトインのステージです。<span class="wintitle">Preprocessing</span> は常に最初のステージに、<span class="wintitle">Postprocessing</span> は常に最後のステージになります。デフォルトでは、<span class="wintitle">Default</span> という名前のステージが 1 つ存在します。 </p> <p> <b>新しい処理ステージを追加するには</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> <span class="filepath">Transformation.cfg</span> ウィンドウで <span class="uicontrol">Stages</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Stage</span> をクリックします。 </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> 新しいステージの名前を入力します。 </li> 
      </ul> </p> <p> <b>既存の処理ステージを削除するには</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> 削除するステージに対応する番号を右クリックし、「<span class="uicontrol">&lt;</span>#stage_number<i>&gt;<span class="uicontrol"></span> を削除</i>」をクリックします。 </li> 
      </ul> </p> <p> <p>注意：<span class="wintitle">変換データセットインクルード</span>ファイルで Stage を指定するときは、ここに入力したステージの名前と完全に一致させる必要があります。データセットインクルードファイルについて詳しくは、「データセットインクルードフ <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> ァイル」を参照してくだ </a>さい。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time </td> 
      <td colname="col2"> <p>(オプション)データのフィルター。タイムスタンプがこの時刻以後（この時刻を含む）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、July 29 2013 00:00:00 EDT を <span class="wintitle">Start Time</span> として指定した場合、米国東部夏時間の 2013 年 7 月 29 日 12:00:00 AM 以降のデータが対象となります。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">タイムゾーンのコード</a>を参照してください。 </p> <p> <p>注意：Start Time の値を指定した場合、Start Time という名前のパラメーターが設定され、データセット構築の変換段階全体で適用されます。パラメーターについて詳しくは、「データセットインクルード <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> ファイルでのパラメーターの定義」を参照してくだ </a>さい。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> (オプション)データセット構築の変換段階における変換は、<span class="wintitle">変換データセットインクルード</span>ファイルに定義することをお勧めします。詳しくは、変換データセットインクルードフ <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> ァイル（英語のみ）を参照してくだ </a>さい。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> タイムゾーン </td> 
      <td colname="col2"> <p>データセットプロファイルのタイムゾーン。タイムゾーンは、時刻の変換や時間ディメンションの作成に使用されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> タイムゾーン </a>. </p> <p> <p>注意：<span class="filepath">Log Processing.cfg</span> ファイルで定義した Time Zone パラメーターは、時刻の変換にのみ使用されます。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
1. で、列 [!DNL Profile Manager]ののチェックマークを右ク [!DNL Transformation.cfg]リッ [!DNL User] クし、> **[!UICONTROL Save to]** * **[!UICONTROL dataset profile name]** をクリックして、ローカルに適用した変更を有効にします。 データセットプロファイルの同期後、データの再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

   データの再処理と再変換について詳しくは、再処理と再変換 [を参照してください](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
