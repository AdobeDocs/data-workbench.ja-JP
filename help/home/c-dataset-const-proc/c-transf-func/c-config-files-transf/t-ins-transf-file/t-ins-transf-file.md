---
description: Data Workbench の Transform.cfg ファイルには、ログのソース、データ変換およびエクスポーターを定義するパラメーターが含まれています。
title: Transform.cfg ファイル
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 79%

---

# Transform.cfg ファイル{#the-transform-cfg-file}

Data Workbench の Transform.cfg ファイルには、ログのソース、データ変換およびエクスポーターを定義するパラメーターが含まれています。

定義した変換は、Sensor（[!DNL .vsl]ファイル）で収集された生データや、テキストファイル、XMLファイル、ODBC準拠のデータベースに含まれる生データを操作し、既存のフィールドに出力したり、現在のデータを上書きしたり、新しく定義されたフィールドに出力します。

変換機能を設定するには、イベントデータのエクスポートに使用するプロファイルの Dataset フォルダーに存在する、Data Workbench の [!DNL Transform.cfg] ファイルを編集します。通常、変換機能には、このプロファイルがメインで使用されます（つまり、実行するデータ処理は、主に Data Workbench の [!DNL Transform.cfg] ファイルで定義します）。継承されたプロファイルの[!DNL Log Processing Dataset Include]ファイルに指定された処理命令は、Data Workbenchの[!DNL Transform.cfg]ファイルに指定された処理命令に加えて適用されることに注意する必要があります。

データセットインクルードファイルについて詳しくは、[データセットインクルードファイル](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。

エクスポート対象データを Data Workbench サーバークラスターで処理する場合、そのクラスター内の個々の処理サーバー（DPU）によってデータが処理されます。ただし、出力データが書き込まれるのは、1 つ目の DPU（[!DNL profile.cfg] ファイルの 0 番目の処理サーバー）のローカルファイルシステムだけです。

**Data Workbench の Transform.cfg ファイルを編集するには**

1. データを書き出すプロファイル内で[!DNL Profile Manager]を開き、**[!UICONTROL Dataset]**&#x200B;をクリックしてディレクトリの内容を表示します。
1. data workbench [!DNL Transform.cfg]の横のチェックマークを右クリックし、 **[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL from the workbench]**&#x200B;をクリックします。 Data Workbenchの[!DNL Transform.cfg]ウィンドウが表示されます。
1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> パラメーター </th> 
    <th colname="col2" class="entry"> 説明 </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> End Time </td> 
    <td colname="col2"> <p>（オプション）データのフィルター。タイムスタンプがこの時刻より前（この時刻は含まず）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> 例えば、July 29 2013 00:00:00 EDT を <span class="wintitle">End Time</span> として指定した場合、米国東部夏時間の 2013 年 7 月 28 日 11:59:59 PM までのデータが対象となります。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード </a>. </p> <p> Sensor ソースやログファイルソースのパラメーターである Use Start/End Times は、このパラメーターと連動します。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exporters </td> 
    <td colname="col2"> <p>出力データの加工方法や書式をエクスポーターのサブフィールドで指定します。一連のログソース用に複数のエクスポーターを定義できます。出力は、エクスポーターのタイプごとに作成されます。 </p> <p> 次の 3 種類のエクスポーターが存在します。 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> エクスポーターの種類について詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> エクスポーターの定義 </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash Threshold </td> 
    <td colname="col2"> （オプション）より小さな標本（データセットの行）をランダムに抽出するためのサンプリング係数。数値 n に設定した場合、n 件の追跡 ID につき 1 件のみがエクスポート対象として選択され、エクスポート対象の合計行数を 1/n に減らすことができます。すべての行をエクスポートする場合は、Hash Threshold を 1 に設定します。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Log Entry Condition </td> 
    <td colname="col2"> （オプション）ログエントリをエクスポート候補とするかどうかの判断基準となるルールを定義します。<span class="wintitle"> Log Entry Condition </span>の詳細については、 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Log Processing Configuration File </a>を参照してください。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> ログソース </td> 
    <td colname="col2"> <p>データのソース。<span class="wintitle">ログソース</span>には、<span class="filepath">.vsl</span> ファイル、ログファイル、XML ファイルのほか、ODBC に準拠したデータベースからのデータを使用できます。<span class="wintitle">ログソース</span>について詳しくは、<a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">ログ処理設定ファイル</a>を参照してください。 </p> <p> <span class="wintitle">Transform</span> は、すべてのソースデータが、辞書式順序に基づいて並べられた入力ファイル内で時系列順になっていることを前提としています。この要件が満たされない場合、基準日の計算が不正確となり、出力ファイルを閉じた後に別の入力データが処理されることがあります。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offline Mode </td> 
    <td colname="col2"> <p>（オプション）true または false。true の場合、<span class="wintitle"></span>データ処理の開始時点で、すべての入力ファイルが存在していることを前提とした動作になります。<span class="wintitle"></span>その時点で存在する入力データの読み取りが完了すると、他のデータの到着を待たず、出力ファイルがすべて閉じられます。デフォルト値は false です。 </p> <p> <p>注意：<span class="wintitle">Offline Mode</span> を true に設定した場合、<span class="wintitle">Transform</span> の処理が開始される前に、すべてのソースデータが存在している必要があります。出力ファイルを閉じた後に追加データが受信された場合、<span class="filepath">VisualServer.log</span> ファイルに警告メッセージが生成されます。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Reprocess </td> 
    <td colname="col2"> <p>（オプション）ここには任意の文字またはその組み合わせを入力できます。このパラメーターに変更を加えて <span class="wintitle">Transform</span> コンピューターにファイルを保存すると、データの再処理が開始されます。 </p> <p> データの再処理について詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">再処理と再変換</a>を参照してください。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Stages </td> 
    <td colname="col2"> <p>（オプション）<span class="wintitle">ログ処理データセットインクルード</span>ファイルで使用できる（Data Workbench の <span class="filepath">Transform.cfg</span> ファイルに加えて実行される）処理ステージの名前。<span class="wintitle">ログ処理データセットインクルード</span>ファイル内に定義された変換の順序付けを行うことができます。複数の<span class="wintitle">ログ処理データセットインクルード</span>ファイルに変換を定義してあるとき、エクスポートプロセスの決まったポイントで特定の変換を実行したい場合に、このパラメーターが非常に役立ちます。 </p> <p> <span class="wintitle">ログ処理データセットインクルード</span>ファイル内の各変換が、データのエクスポートの過程でどのような順序で実行されるかは、ここにリストしたステージの順序によって決まります。<span class="wintitle">Preprocessing</span> と <span class="wintitle">Postprocessing</span> はビルトインのステージです。<span class="wintitle">Preprocessing</span> は常に最初のステージに、<span class="wintitle">Postprocessing</span> は常に最後のステージになります。デフォルトでは、<span class="wintitle">Default</span> という名前のステージが 1 つ存在します。 </p> <p> <b>新しい処理ステージを追加するには</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> Data Workbench の <span class="filepath">Transform.cfg</span> ウィンドウで <span class="uicontrol">Stages</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Stage</span> をクリックします。 </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> 新しいステージの名前を入力します。 </li> 
      </ul> <p> <b>既存の処理ステージを削除するには</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> 削除するステージに対応する番号を右クリックし、「<span class="uicontrol">&lt;</span>#stage_number<i>&gt;<span class="uicontrol"></span> を削除</i>」をクリックします。 </li> 
      </ul> <p> <p>注意：<span class="wintitle">ログ処理データセットインクルード</span>ファイルで Stage を指定するときは、ここに入力したステージの名前と完全に一致させる必要があります。データセットインクルードファイルについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">データセットインクルードファイル</a>を参照してください。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Start Time </td> 
    <td colname="col2"> <p>（オプション）データのフィルター。タイムスタンプがこの時刻以後（この時刻を含む）のログエントリを抽出します。この時刻には、次のいずれかの形式を使用することをお勧めします。 </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p> 例えば、July 29 2013 00:00:00 EDT を Start Time として指定した場合、米国東部夏時間の 2013 年 7 月 29 日 12:00:00 AM 以降のデータが対象となります。 </p> <p> タイムゾーンの指定は必須です。タイムゾーンを指定しなかった場合に、デフォルトで GMT に設定されることはありません。Data Workbench サーバーでサポートされるタイムゾーンの略称一覧については、 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> タイムゾーンのコード </a>. </p> <p> <p>注意：Sensor ソースやログファイルソースのパラメーターである Use Start/End Times は、このパラメーターと連動します。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformations </td> 
    <td colname="col2"> <p>（オプション）データに適用する変換を定義します。利用可能な変換のタイプについて詳しくは、 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> データ変換 </a>. </p> <p> <p>注意：次のタイプの変換は、Data Workbench の <span class="filepath">Transform.cfg</span> ファイルで定義されている場合にしか正しく機能しません。 </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>出力ファイルを閉じた後にさらに別のデータを受信した場合（前掲の表の「[!DNL Log Sources]」と「[!DNL Offline Mode]」を参照）、[!DNL Transform] は、その追加データを使用して新しい出力ファイルを作成します。新しい出力ファイルの名前は、元の出力ファイル名の拡張子の前に、バージョン番号を括弧で囲んで追加することによって生成されます。例えば、元の出力ファイルが[!DNL 20070701-ABC.vsl]の場合、このファイルの後続のバージョンの名前は[!DNL 20070701-ABC(1).vsl]、[!DNL 20070701-ABC(2).vsl]のようになります。 複数バージョンのファイルを Data Workbench サーバーの入力として使用すると、処理エラーとなる場合があります。
>
>
>複数バージョンの出力ファイルが作成されるのは好ましくありません。辞書式順序に基づいて並べられた入力ファイル内ですべてのソースデータが時系列順になっていることを確認し、さらに、[!DNL Offline Mode] を true に設定する場合は、すべてのソースデータが処理の開始時点で存在することを確認してください。詳しくは、前述の表の[!DNL Log Sources]と[!DNL Offline Mode]のエントリを参照してください。

1. **[!UICONTROL Transformations]**&#x200B;を右クリックし、**[!UICONTROL Add new]** / **[!UICONTROL Transformation type]**&#x200B;をクリックして、変換を追加します。 変換のフィールドに必要事項を入力します。

   変換機能で使用できる変換の説明と例については、[データ変換](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)を参照してください。

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。
1. ローカルで作成した変更を有効にするには、[!DNL Profile Manager]で、[!DNL User]列のdata workbench [!DNL Transform.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]** / **[!UICONTROL profile name]**&#x200B;をクリックします。profile nameは、データをエクスポートするプロファイルの名前です。 プロファイルの同期後、データの再処理が開始されます。

   >[!NOTE]
   >
   >書き出し用のデータの再処理について詳しくは、[再処理と再変換](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)を参照してください。
