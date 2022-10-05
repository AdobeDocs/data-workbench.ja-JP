---
description: データセットプロファイルの Transformation.cfg ファイルを編集する手順について説明します。
title: 変換設定ファイルの編集
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 75%

---

# 変換設定ファイルの編集{#editing-the-transformation-configuration-file}

{{eol}}

データセットプロファイルの Transformation.cfg ファイルを編集する手順について説明します。

1. データセットプロファイル内で、 [!DNL Profile Manager] をクリックし、 **[!UICONTROL Dataset]** 内容を表示する。

   を開き、使用する方法については、 [!DNL Profile Manager]を参照し、 *Data Workbenchユーザーガイド*.

   >[!NOTE]
   >
   >Dataset ディレクトリ内には、Transformation サブディレクトリが存在する場合があります。 このサブディレクトリには、 [!DNL Transformation Dataset Include] 継承された 1 つ以上のプロファイルに対して作成されたファイル。 詳しくは、 [!DNL Transformation Dataset Include] ファイル： [データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. の横のチェックマークを右クリックします。 [!DNL Transformation.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. この [!DNL Transformation.cfg] ウィンドウが表示されます。

   また、 [!DNL Transformation.cfg] ファイル [!DNL Transformation Dependency Map]. 詳しくは、 [!DNL transformation dependency maps]を参照してください。 [データセット設定ツール](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   Data Workbench ウィンドウ内で [!DNL Transformation.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、ショートカットを使用して、1 つの設定ファイル ( [!DNL .cfg]) を別のに置き換えます。

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] 継承プロファイルのファイルには、次の表で説明するパラメーターのサブセットと、追加のパラメーターが含まれています。 詳しくは、 [!DNL Transformation Dataset Include] ファイル： [データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

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
      <td colname="col2"> <p>（オプション）。データのフィルター。タイムスタンプがこの時刻より前（この時刻は含まず）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 2013 年 1 月 1 日 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 2013 年 1 月 1 日 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、「July 29 2013 00」:00:「00 EDT」（終了時間）には、2013 年 7 月 28 日 (11) までのデータが含まれます:59:米国東部標準時の午後 59 時。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード </a>. </p> <p> <p>注意：End Time の値を指定した場合、End Time という名前のパラメーターが設定され、データセット構築の変換段階全体で適用されます。パラメーターについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義 </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拡張ディメンション </td> 
      <td colname="col2"> （オプション）。拡張ディメンションは、<span class="wintitle">変換データセットインクルード</span>ファイルに定義することをお勧めします。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 変換データセットインクルードファイル </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold </td> 
      <td colname="col2"> <p>（オプション）。より小さな標本（データセットの行）をランダムに抽出するためのサンプリング係数。数値 n に設定した場合、n 件の追跡 ID につき 1 件のみがデータセットに組み入れられ、データセットの合計行数を 1/n に減らすことができます。100％の精度が必要なデータセットを作成する（つまりすべての行を対象とする）には、Hash Threshold を 1 に設定します。 </p> <p> <span class="filepath">Log Processing.cfg</span> ファイルと <span class="filepath">Transformation.cfg</span> ファイルの両方に Hash Threshold を指定した場合、それぞれの値が順に適用されるのではなく、いずれか大きい方の値だけが適用されます。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition </td> 
      <td colname="col2"> （オプション）。ログ処理から出力されたログエントリをデータセットプロファイルに含めるかどうかの判断基準となるルールを定義します。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> ログ記録条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 新規訪問者条件 </td> 
      <td colname="col2"> （オプション）。Web データ用。データに訪問者を含めるかどうかの判断基準となるルールを定義します。<span class="wintitle">New Visitor Condition</span> は、特定の訪問者の（時系列順に並んだ）ログのうち、データセットに使用する最初のエントリを定義します。それ以降、この条件を満たしているかどうかに関係なく、同じ訪問者のすべてのログエントリがデータセットに組み入れられます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> 新規訪問者条件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess </td> 
      <td colname="col2"> <p>（オプション）。ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えてファイルを保存すると、データの再変換が開始されます。 </p> <p> データの再処理について詳しくは、 <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 再処理と再変換 </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Schema Checking </td> 
      <td colname="col2"> true または false。true の場合、データセットの破損の問題を Data Workbench サーバーが特定し、その Trace ディレクトリ内のログファイルに問題に関する情報を記録します。デフォルト値は true です。このパラメーターは常に true にしておくことをお勧めします。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages </td> 
      <td colname="col2"> <p>（オプション）。<span class="wintitle">変換データセットインクルード</span>ファイルで使用できる処理ステージの名前。処理ステージにより、<span class="wintitle">変換データセットインクルード</span>ファイル内に定義された変換の順序付けを行うことができます。複数の<span class="wintitle">変換データセットインクルード</span>ファイルに変換を定義してあるとき、変換の決まったポイントで特定の変換を実行したい場合に、このパラメーターが非常に役立ちます。 </p> <p> <span class="wintitle">変換データセットインクルード</span>ファイル内の各変換が、変換の過程でどのような順序で実行されるかは、ここにリストしたステージの順序によって決まります。<span class="wintitle">Preprocessing</span> と <span class="wintitle">Postprocessing</span> はビルトインのステージです。<span class="wintitle">Preprocessing</span> は常に最初のステージに、<span class="wintitle">Postprocessing</span> は常に最後のステージになります。デフォルトでは、<span class="wintitle">Default</span> という名前のステージが 1 つ存在します。 </p> <p> <b>新しい処理ステージを追加するには</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> <span class="filepath">Transformation.cfg</span> ウィンドウで <span class="uicontrol">Stages</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Stage</span> をクリックします。 </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> 新しいステージの名前を入力します。 </li> 
      </ul> </p> <p> <b>既存の処理ステージを削除するには</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> 削除するステージに対応する番号を右クリックし、「<span class="uicontrol">&lt;</span>#stage_number<i>&gt;<span class="uicontrol"></span> を削除</i>」をクリックします。 </li> 
      </ul> </p> <p> <p>注意：<span class="wintitle">変換データセットインクルード</span>ファイルで Stage を指定するときは、ここに入力したステージの名前と完全に一致させる必要があります。データセットインクルードファイルについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> データセットインクルードファイル </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time </td> 
      <td colname="col2"> <p>（オプション）。データのフィルター。タイムスタンプがこの時刻以後（この時刻を含む）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 2013 年 1 月 1 日 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 2013 年 1 月 1 日 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、July 29 2013 00 を指定します。:00:00 EDT を <span class="wintitle"> 開始時間 </span> には、2013 年 7 月 29 日 (PT) から 12 日 (PT) 以降のデータが含まれます。:00:午前 00 時。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード </a>. </p> <p> <p>注意：Start Time の値を指定した場合、Start Time という名前のパラメーターが設定され、データセット構築の変換段階全体で適用されます。パラメーターについて詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> データセットインクルードファイルでのパラメーターの定義 </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> （オプション）。データセット構築の変換段階における変換は、<span class="wintitle">変換データセットインクルード</span>ファイルに定義することをお勧めします。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 変換データセットインクルードファイル </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> タイムゾーン </td> 
      <td colname="col2"> <p>データセットプロファイルのタイムゾーン。タイムゾーンは、時刻の変換や時間ディメンションの作成に使用されます。詳しくは、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> タイムゾーン </a>. </p> <p> <p>注意：<span class="filepath">Log Processing.cfg</span> ファイルで定義した Time Zone パラメーターは、時刻の変換にのみ使用されます。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL Transformation.cfg]内 [!DNL User] 列、「 **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** ローカルで行った変更を有効にする データセットプロファイルの同期後、データの再変換が開始されます。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。

   データの再処理または再変換について詳しくは、 [再処理と再変換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
