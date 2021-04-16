---
description: 任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。
title: セグメントのエクスポート用の設定
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 70%

---

# セグメントのエクスポート用の設定{#configure-segments-for-export}

任意の可算ディメンションの要素からなるセグメントを作成してから、そのセグメントのデータをバッチまたは継続的なリアルタイムベースでタブ区切りファイルに出力できます。

セグメントをエクスポートするたびに、そのセグメントに含まれているすべてのディメンションエレメントの指標またはディメンションデータを出力します。他のシステムでデータを簡単にロードできるように、出力データのフォーマットを制御することができます。

>[!NOTE]
>
>レポートディメンションは、参照用に[!DNL report time.metric]ファイルを使用しているので、エクスポートできません。 回避策として、ハードコーディングした [!DNL report time.metric] をプロファイルに配置すると、セグメントのエクスポートで、そのファイルをレポートディメンションの参照ポイントとして使用できます。ただし、[!DNL report time.metric] は、プロファイルの基準時刻に基づいて自動的に更新されないので、レポートディメンションの参照を変更する場合は、ハードコーディングされた [!DNL report time.metric] ファイルを変更する必要があります。

セグメントをエクスポート用に設定するには、[!DNL .export]ファイルを開いて編集する必要があります。

1. [!DNL Profile Manager]で、[!DNL File]列の&#x200B;**[!UICONTROL Export]**&#x200B;ディレクトリをクリックして、その内容を表示します。

       Export ディレクトリが存在しない場合は、次の手順に従って作成します。
   
   1. Data Workbenchのインストールディレクトリに移動します。
   1. 作業しているプロファイルのディレクトリを開きます。
   1. プロファイルディレクトリ内に、「Export」という名前の新しいディレクトリを作成します。

1. [!DNL Profile Manager]で、Exportディレクトリの[!DNL User]列の空のセルを右クリックし、**[!UICONTROL Create]**/**[!UICONTROL New Segment Export]**&#x200B;をクリックします。

   [!DNL New Segment Export.export]という名前のファイルが、エクスポートの[!DNL File]列に表示されます。

1. ファイルの[!DNL User]列を右クリックし、Fileパラメーターに新しい名前を入力して、新しいファイルの名前を変更します。
1. ファイルの[!DNL User]列を右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックして、新しいファイルを開きます。

   [!DNL .export]ファイルの設定ウィンドウが表示されます。

1. **[!UICONTROL Query]**&#x200B;をクリックし、次の表の説明に従って[!DNL .export]ファイルのフィールドを変更します。

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
   <td colname="col2"> <p>（オプション）出力ファイルが作成された後に実行するプログラム。このフィールドは、シェルコマンドではなく実行可能ファイル（<span class="filepath">.exe</span> ファイル）を参照する必要があります。 </p> <p>注意：コマンドパラメーターにスペースが含まれている場合、セグメントエクスポートは失敗します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> フィルター </td> 
   <td colname="col2"> <p>（オプション）名前付きのフィルターまたはフィルター式。フィルターエディターを使用して名前付きのフィルターを作成し、そのフィルターの名前をここに入力するか、またはフィルター式自体を入力できます。 </p> <p>フィルターエディターの詳細については、「 <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> フィルターエディター </a>. フィルター式の構文について詳しくは、「<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15">フィルター式の構文</a>」を参照してください。 </p> <p>フィルターに一致するレベルのエレメントがエクスポートされます。その他すべてのエレメントはエクスポートされません。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Level </td> 
   <td colname="col2"> <p>エレメントがエクスポートされる可算ディメンション。 </p> <p>例：訪問者のレベルでは、各訪問者に対して 1 行のデータがエクスポートされます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output File </td> 
   <td colname="col2"> <p>エクスポートされたデータのパスとファイル名。プロファイルがData Workbenchサーバークラスター上で実行されている場合、各Data Workbenchサーバーはデータの一部を含む出力ファイルを書き込みます。 </p> <p>Data Workbenchサーバーのインストールディレクトリには、出力ファイルを保存できるExportsディレクトリが含まれています。 例えば、<span class="filepath">Exports\訪問者セグメント.txt</span> と入力できます。ここで、<span class="filepath">訪問者セグメント.txt</span> はエクスポートされたデータを含むファイルの名前です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Format </td> 
   <td colname="col2"> 各レベルエレメントでエクスポートされる指標またはディメンションデータ。出力がタブ区切り形式のファイルの場合、各フィールドはタブ文字で区切られて、適切な改行文字で終わる必要があります。詳しくは、「 <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> 出力形式について </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule End Time </td> 
   <td colname="col2"> <p>（オプション）タイムゾーンを含む、スケジュールの終了日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に終了します。ただし、出力ファイルは、定義が変更されると再生成されます。このフィールドは、Schedule Every を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Every </td> 
   <td colname="col2"> （オプション）出力ファイルを再生成する頻度。時間、日、週、月の値がサポートされます。出力ファイルは、定義が変更されると再生成されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Schedule Start Time </td> 
   <td colname="col2"> <p>（オプション）タイムゾーンを含む、スケジュールの開始日時。 </p> <p>形式：YYYY-MM-DD hh:mm &lt;time zone&gt; </p> <p>例：2013-08-01 12:01 EDT </p> <p>スケジュールされたエクスポートはこの時間に開始されます。スケジュールは、この時間に対して相対的な間隔となります。このフィールドは、<span class="wintitle">Schedule Every</span> を定義しないと意味を持ちません。タイムゾーン設定の詳細については、『<i>データセット設定ガイド</i>』を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Limit (sec) </td> 
   <td colname="col2"> （オプション）セグメントのエクスポートの生成処理で許容される最大時間。指定した時間が経過すると、エクスポートが最初からやり直されます。この値を 0 に設定すると、制限がなくなります。デフォルト値は 600 秒です。 </td> 
  </tr> 
 </tbody> 
</table>

1. ウィンドウ上部の&#x200B;**[!UICONTROL (New)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
1. 作業プロファイルのすべてのユーザーがこのファイルを利用できるようにするには、[!DNL User]列に作成した[!DNL .export]ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]**>*&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL .export]ファイルをData Workbenchサーバーに保存すると、スケジュール開始時間が未来の日時に設定されている場合でも、エクスポートは直ちに1回実行されます。

   以下はサンプルの[!DNL .export]ファイルです。

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >サンプルの[!DNL Visitor Segment.export]ファイルは、訪問者セグメントフィルターを参照しています。 このフィルターの定義を変更すると、エクスポートの定義も変更されます。
