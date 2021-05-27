---
description: 設定ファイル Log Processing Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 83%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

設定ファイル Log Processing Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。

ソースの追加と削除を含め、[!DNL Log Processing Mode.cfg] ファイルに変更を加えても、データの再処理は行われません。

**データセットプロファイルの Log Processing Mode.cfg ファイルを編集するには**

1. データセットプロファイル内で[!DNL Profile Manager]を開き、 **[!UICONTROL Dataset]**&#x200B;をクリックして内容を表示します。

   >[!NOTE]
   >
   >[!DNL Log Processing Mode.cfg]ファイルが目的のプロファイルのディレクトリにない場合は、Data Workbenchサーバーコンピューター上のBaseディレクトリからプロファイルのディレクトリにこのファイルをコピーする必要があります。

   [!DNL Profile Manager,]を開いて使用する方法については、『*Data Workbenchユーザーガイド*』を参照してください。

1. 設定ファイルの名前の横のチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL from the workbench]**&#x200B;をクリックします。 設定ウィンドウが表示されます。
1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   >[!NOTE]
   >
   >[!DNL Log Processing Mode.cfg]ファイル内の一部のパラメーターには、[!DNL Fast Input]または[!DNL Fast Merge]を含む名前が付けられます。 [!DNL Fast Input] は、データセット構築のログ処理段階を指し、データセットの処理にかかる合計時間の約半分を占めます。[!DNL Fast Merge] は、データセット構築の変換段階を指します。先行するログ処理があって初めて使用されます。[!DNL Fast Merge] は、ファイルの変更による再変換中には発生し [!DNL Transformation Dataset Configuration] ません。[!DNL Fast Input]と同様に、 [!DNL Fast Merge]もデータセット処理時間の約半分を占めます。

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> パラメーター </th> 
      <th colname="col2" class="entry"> 説明 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Cloud Bytes </td> 
      <td colname="col2"> <p>データ変換の効率に関係するチューニングパラメーター。デフォルト値は 128000000 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decision Ratio </td> 
      <td colname="col2"> <p>データの処理をリアルタイムモードから <span class="wintitle">Fast Input</span> モード（その後 <span class="wintitle">Fast Merge</span> モード）に移行するタイミングを、ログの総バイト数と未読バイト数の比で指定するチューニングパラメーター。 </p> <p> デフォルト値は 200 です。この場合、未読ログデータが総データの 1/200 に達すると、システムがリアルタイムモードから <span class="wintitle">Fast Input</span> モードに移行します。Decision Ratio を大きくすると、<span class="wintitle">Fast Input</span> モードに移行しやすくなり、小さくすると、<span class="wintitle">Fast Input</span> モードに移行しづらくなります。 </p> <p> <p>注意：このパラメーターを 0 に設定すると、初回処理も含め一切 <span class="wintitle">Fast Input</span> モードに移行しなくなります。このパラメーターを 1.1 に設定すると、初回処理時には <span class="wintitle">Fast Input</span> に移行しますが、その後の処理では移行しません。0 ～ 1.1 の値は推奨されません。このパラメーターの設定について詳しくは、アドビにお問い合わせください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input FIFO Bytes </td> 
      <td colname="col2"> <p>データ処理時におけるメモリ使用量とシステムパフォーマンス間のバランスを調整するチューニングパラメーター。デフォルト値は 120000000 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Merge Buffer Bytes </td> 
      <td colname="col2"> <p>データ処理時におけるメモリ使用量とシステムパフォーマンス間のバランスを調整するチューニングパラメーター。デフォルト値は 128000000 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline Sources </td> 
      <td colname="col2"> <p>オフラインログソースのマスク。 </p> <p> <b> オフラインソースを指定するには</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> <span class="uicontrol">Offline Sources</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Source</span> をクリックします。 </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 新しいソースのパラメーターに、ログシーケンスのマスクを入力します。ファイル名が YYYYMMDD-<i>SENSORID</i>.vsl 形式の Sensor ログソースの場合、マスクは <i>SENSORID</i> です。SENSORID の大文字と小文字は区別されます。ログファイルログソースの場合、<span class="wintitle">Mask Pattern</span> によって抽出された文字列がマスクになります。<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">ログファイル</a>を参照してください。 </li> 
      </ul> </p> <p> Offline Sources に属しているソースは、追加したり削除したりしても、データセットの再処理は実行されません。 </p> <p> 基準日時の測定は、プロファイルのオンラインソースの処理に対して維持されます。オフラインソースが再びオンラインになると、そのソースから送られてくるログファイルの処理が再開されます。 </p> <p> ソースがオンラインに戻ったらすぐに、Offline Sources からそのソースを削除する必要があります。削除しなかった場合、Data Workbench サーバーは、ソースからデータが送信されている限り、そのソースをオンラインソースとして処理し、基準日時を更新します。そのソースが再度オフラインになった場合、基準日時の測定が停止します。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Paused </td> 
      <td colname="col2"> true または false。true の場合、新しいデータは処理されず、データセットに追加されません。デフォルト値は false です。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time Delay </td> 
      <td colname="col2"> データセットに組み入れるデータを Data Workbench サーバーが処理する際の、データ間の待機時間（秒数）。この値をゼロに設定すると、到着したデータが、可能な限りリアルタイムで処理されます。デフォルト値はゼロ（0）ですが、この値を増やすことで、CPU にかかる負荷を抑えることができます。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time FIFO Bytes </td> 
      <td colname="col2"> <p>データセットへの組み入れ処理を待つデータを蓄えておくためのメモリの量（バイト）。Real Time Delay に指定した秒数に応じて変更が必要となる場合があります。デフォルト値は 16000000 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Save Interval (sec) </td> 
      <td colname="col2"> <p>Data Workbench サーバーでその状態ファイルが保存される頻度。デフォルト値は 3600 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   Data Workbench ウィンドウ内で [!DNL Log Processing Mode.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、設定ファイル([!DNL .cfg])間でテキストをコピーして貼り付ける際にも、ショートカットを使用できます。

1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。
1. [!DNL Profile Manager]で、[!DNL User]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / **[!UICONTROL datasetprofile name]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。
