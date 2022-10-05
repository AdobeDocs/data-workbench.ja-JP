---
description: 任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。
title: セグメントのエクスポート用の設定
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 70%

---

# セグメントのエクスポート用の設定{#configure-segments-for-export}

{{eol}}

任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。

セグメントをエクスポートするたびに、そのセグメントに含まれているすべてのディメンションエレメントの指標またはディメンションデータを出力します。他のシステムでデータを簡単にロードできるように、出力データのフォーマットを制御することができます。

>[!NOTE]
>
>レポートディメンションは、 [!DNL report time.metric] ファイルを参照してください。 回避策として、ハードコーディングした [!DNL report time.metric] をプロファイルに配置すると、セグメントのエクスポートで、そのファイルをレポートディメンションの参照ポイントとして使用できます。ただし、[!DNL report time.metric] は、プロファイルの基準時刻に基づいて自動的に更新されないので、レポートディメンションの参照を変更する場合は、ハードコーディングされた [!DNL report time.metric] ファイルを変更する必要があります。

セグメントをエクスポート用に設定するには、を開いて編集する必要があります。 [!DNL .export] ファイル。

1. 内 [!DNL Profile Manager]、 **[!UICONTROL Export]** ディレクトリ [!DNL File] 列の内容を表示します。

       Export ディレクトリが存在しない場合は、次の手順に従って作成します。
   
   1. Data Workbenchのインストールディレクトリに移動します。
   1. 作業しているプロファイルのディレクトリを開きます。
   1. プロファイルディレクトリ内に、「Export」という名前の新しいディレクトリを作成します。

1. 内 [!DNL Profile Manager]をクリックし、 [!DNL User] 列をクリックし、 **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   という名前のファイル [!DNL New Segment Export.export] が [!DNL File] 列を開きます。

1. 新しいファイルの名前を変更するには、 [!DNL User] 列を編集し、File パラメーターに新しい名前を入力します。
1. 新しいファイルを開くには、 [!DNL User] 列をクリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   の設定ウィンドウ [!DNL .export] ファイルが表示されます。

1. クリック **[!UICONTROL Query]**&#x200B;を編集し、 [!DNL .export] 次の表の説明に従って、ファイルを編集します。

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> パラメーター </th> 
   <th colname="col2" class="entry"> 入力する情報 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> コマンド </td> 
   <td colname="col2"> <p>（オプション）。出力ファイルが作成された後に実行するプログラム。このフィールドは、シェルコマンドではなく実行可能ファイル（<span class="filepath">.exe</span> ファイル）を参照する必要があります。 </p> <p>注意：コマンドパラメーターにスペースが含まれている場合、セグメントエクスポートは失敗します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルター </td> 
   <td colname="col2"> <p>（オプション）。名前付きのフィルターまたはフィルター式。フィルターエディターを使用して名前付きのフィルターを作成し、そのフィルターの名前をここに入力するか、またはフィルター式自体を入力できます。 </p> <p>フィルターエディターの詳細については、「 <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> フィルターエディター </a>. フィルター式の構文の詳細については、「 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> フィルター式の構文 </a>. </p> <p>フィルターに一致するレベルのエレメントがエクスポートされます。その他すべてのエレメントはエクスポートされません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Level </td> 
   <td colname="col2"> <p>エレメントがエクスポートされる可算ディメンション。 </p> <p>例：訪問者のレベルでは、各訪問者に対して 1 行のデータがエクスポートされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output File </td> 
   <td colname="col2"> <p>エクスポートされたデータのパスとファイル名。プロファイルがData Workbenchサーバークラスタ上で実行されている場合、各Data Workbenchサーバーはデータの一部を含む出力ファイルを書き込みます。 </p> <p>Data Workbenchサーバーのインストールディレクトリには、出力ファイルを保存できる Exports ディレクトリが含まれています。 例えば、<span class="filepath">Exports\訪問者セグメント.txt</span> と入力できます。ここで、<span class="filepath">訪問者セグメント.txt</span> はエクスポートされたデータを含むファイルの名前です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Format </td> 
   <td colname="col2"> 各レベルエレメントでエクスポートされる指標またはディメンションデータ。出力がタブ区切り形式のファイルの場合、各フィールドはタブ文字で区切られて、適切な改行文字で終わる必要があります。詳しくは、「 <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> 出力形式について </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule End Time </td> 
   <td colname="col2"> <p>（オプション）。タイムゾーンを含む、スケジュールの終了日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に終了します。ただし、出力ファイルは、定義が変更されると再生成されます。このフィールドは、Schedule Every を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Every </td> 
   <td colname="col2"> （オプション）。出力ファイルを再生成する頻度。時間、日、週、月の値がサポートされます。出力ファイルは、定義が変更されると再生成されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Start Time </td> 
   <td colname="col2"> <p>（オプション）。タイムゾーンを含む、スケジュールの開始日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に開始されます。スケジュールは、この時間に対して相対的な間隔となります。このフィールドは、<span class="wintitle">Schedule Every</span> を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Limit (sec) </td> 
   <td colname="col2"> （オプション）。セグメントのエクスポートの生成処理で許容される最大時間。指定した時間が経過すると、エクスポートが最初からやり直されます。この値を 0 に設定すると、制限がなくなります。デフォルト値は 600 秒です。 </td> 
  </tr> 
 </tbody> 
</table>

1. 右クリック **[!UICONTROL (New)]** ウィンドウの上部で、「 **[!UICONTROL Save]**.
1. 作業プロファイルのすべてのユーザーがこのファイルを使用できるようにするには、作成した [!DNL .export] ファイルを [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >の保存 [!DNL .export] ファイルをData Workbench・サーバに送信すると、Schedule Start Time が未来の日時に設定されている場合でも、エクスポートが即座に 1 回実行されます。

   以下はサンプルです [!DNL .export] ファイル。

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >この [!DNL Visitor Segment.export] ファイルの例は、訪問者セグメントフィルターを指します。 このフィルターの定義を変更すると、エクスポートの定義も変更されます。
