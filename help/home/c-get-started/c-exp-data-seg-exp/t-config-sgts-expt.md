---
description: 任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。
solution: Analytics
title: 書き出すセグメントの設定
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configure segments for export{#configure-segments-for-export}

任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。

セグメントをエクスポートするたびに、そのセグメントに含まれているすべてのディメンションエレメントの指標またはディメンションデータを出力します。他のシステムでデータを簡単にロードできるように、出力データのフォーマットを制御することができます。

>[!NOTE]
>
>You cannot export reporting dimensions, because they use a [!DNL report time.metric] file for reference. 回避策として、ハードコーディングした [!DNL report time.metric] をプロファイルに配置すると、セグメントのエクスポートで、そのファイルをレポートディメンションの参照ポイントとして使用できます。ただし、[!DNL report time.metric] は、プロファイルの基準時刻に基づいて自動的に更新されないので、レポートディメンションの参照を変更する場合は、ハードコーディングされた [!DNL report time.metric] ファイルを変更する必要があります。

To configure a segment for export, you must open and edit a [!DNL .export] file.

1. In the [!DNL Profile Manager], click the **[!UICONTROL Export]** directory in the [!DNL File] column to show its contents.

       Export ディレクトリが存在しない場合は、次の手順に従って作成します。
   
   1. Data Workbenchのインストールディレクトリに移動します。
   1. 作業しているプロファイルのディレクトリを開きます。
   1. プロファイルディレクトリ内に、「Export」という名前の新しいディレクトリを作成します。

1. で、Export [!DNL Profile Manager]ディレクトリの列の空のセルを右ク [!DNL User] リックし、/をクリックし **[!UICONTROL Create]** ます **[!UICONTROL New Segment Export]**。

   A file named [!DNL New Segment Export.export] appears in the [!DNL File] column for Export.

1. Rename the new file by right-clicking in the [!DNL User] column for the file and typing the new name in the File parameter.
1. 新しいファイルを開くには、ファイルの列を右ク [!DNL User] リックし、/をクリック **[!UICONTROL Open]** しま **[!UICONTROL from the workbench]**&#x200B;す。

   The configuration window for the [!DNL .export] file appears.

1. Click **[!UICONTROL Query]**, then modify the fields of the [!DNL .export] file as described in the following table:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Command </td> 
   <td colname="col2"> <p>(オプション)出力ファイルが作成された後に実行するプログラム。このフィールドは、シェルコマンドではなく実行可能ファイル（<span class="filepath">.exe</span> ファイル）を参照する必要があります。 </p> <p>注意：コマンドパラメーターにスペースが含まれている場合、セグメントエクスポートは失敗します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルター </td> 
   <td colname="col2"> <p>(オプション)名前付きのフィルターまたはフィルター式。フィルターエディターを使用して名前付きのフィルターを作成し、そのフィルターの名前をここに入力するか、またはフィルター式自体を入力できます。 </p> <p>フィルターエディターの詳細については、「 <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> フィルターエディター </a>. フィルター式の構文について詳しくは、「フィルター式の構 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> 文」を参照してくださ </a>い。 </p> <p>フィルターに一致するレベルのエレメントがエクスポートされます。その他すべてのエレメントはエクスポートされません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Level </td> 
   <td colname="col2"> <p>エレメントがエクスポートされる可算ディメンション。 </p> <p>例：訪問者のレベルでは、各訪問者に対して 1 行のデータがエクスポートされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output File </td> 
   <td colname="col2"> <p>エクスポートされたデータのパスとファイル名。プロファイルがData Workbenchサーバークラスター上で実行されている場合、各Data Workbenchサーバーは、データの一部を含む出力ファイルを書き込みます。 </p> <p>Data Workbenchサーバーのインストールディレクトリには、出力ファイルを保存できるExportsディレクトリが含まれています。 例えば、<span class="filepath">Exports\訪問者セグメント.txt</span> と入力できます。ここで、<span class="filepath">訪問者セグメント.txt</span> はエクスポートされたデータを含むファイルの名前です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Format </td> 
   <td colname="col2"> 各レベルエレメントでエクスポートされる指標またはディメンションデータ。出力がタブ区切り形式のファイルの場合、各フィールドはタブ文字で区切られて、適切な改行文字で終わる必要があります。詳しくは、「 <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> 出力形式について </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule End Time </td> 
   <td colname="col2"> <p>(オプション)タイムゾーンを含む、スケジュールの終了日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に終了します。ただし、出力ファイルは、定義が変更されると再生成されます。このフィールドは、Schedule Every を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Every </td> 
   <td colname="col2"> (オプション)出力ファイルを再生成する頻度。時間、日、週、月の値がサポートされます。出力ファイルは、定義が変更されると再生成されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Start Time </td> 
   <td colname="col2"> <p>(オプション)タイムゾーンを含む、スケジュールの開始日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に開始されます。スケジュールは、この時間に対して相対的な間隔となります。このフィールドは、<span class="wintitle">Schedule Every</span> を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Limit (sec) </td> 
   <td colname="col2"> (オプション)セグメントのエクスポートの生成処理で許容される最大時間。指定した時間が経過すると、エクスポートが最初からやり直されます。この値を 0 に設定すると、制限がなくなります。デフォルト値は 600 秒です。 </td> 
  </tr> 
 </tbody> 
</table>

1. Right-click **[!UICONTROL (New)]** at the top of the window, then click **[!UICONTROL Save]**.
1. To make this file available to all users of the working profile, right-click the check mark for the created [!DNL .export] file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Saving the [!DNL .export] file to the Data Workbench server causes the export to run once immediately, even if the Schedule Start Time is set to a future date and time.

   The following is a sample [!DNL .export] file.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >The [!DNL Visitor Segment.export] file shown in the sample refers to the Visitor Segment filter. このフィルターの定義を変更すると、エクスポートの定義も変更されます。

