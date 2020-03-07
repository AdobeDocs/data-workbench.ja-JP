---
description: 設定ファイル Log Processing Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。
solution: Analytics
title: Log Processing Mode.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Log Processing Mode.cfg{#log-processing-mode-cfg}

設定ファイル Log Processing Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。

ソースの追加と削除を含め、[!DNL Log Processing Mode.cfg] ファイルに変更を加えても、データの再処理は行われません。

**データセットプロファイルの Log Processing Mode.cfg ファイルを編集するには**

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   >[!NOTE]
   >
   >If the [!DNL Log Processing Mode.cfg] file is not located in the directory for the desired profile, you need to copy this file from the Base directory on the data workbench server machine into the profile&#39;s directory.

   For information about opening and working with the [!DNL Profile Manager,] see the *Data Workbench User Guide*.

1. Right-click the check mark next to the configuration file&#39;s name and click **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL from the workbench]**&#x200B;す。 設定ウィンドウが表示されます。
1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   >[!NOTE]
   >
   >Some of the parameters in the [!DNL Log Processing Mode.cfg] file have names that include [!DNL Fast Input] or [!DNL Fast Merge]. [!DNL Fast Input] は、データセット構築のログ処理段階を指し、データセットの処理にかかる合計時間の約半分を占めます。[!DNL Fast Merge] は、データセット構築の変換段階を指します。先行するログ処理があって初めて使用されます。[!DNL Fast Merge] は、ファイルの変更による再変換時には発生し [!DNL Transformation Dataset Configuration] ません。 Like [!DNL Fast Input], [!DNL Fast Merge] is also responsible for approximately half of the dataset processing time.

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
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 新しいソースのパラメーターに、ログシーケンスのマスクを入力します。ファイル名が YYYYMMDD-<i>SENSORID</i>.vsl 形式の Sensor ログソースの場合、マスクは <i>SENSORID</i> です。SENSORID の大文字と小文字は区別されます。ログファイルログソースの場合、<span class="wintitle">Mask Pattern</span> によって抽出された文字列がマスクになります。See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
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

   Data Workbench ウィンドウ内で [!DNL Log Processing Mode.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
1. で、列 [!DNL Profile Manager]内のファイルのチェックマークを右クリックし、 [!DNL User] /をクリックし **[!UICONTROL Save to]** ます **[!UICONTROL datasetprofile name]**。

   >[!NOTE]
   >
   >アドビから提供される内部プロファイルには、変更した設定ファイルを一切保存しないでください。内部プロファイルに対するアップデートをインストールするときに変更内容が上書きされます。
