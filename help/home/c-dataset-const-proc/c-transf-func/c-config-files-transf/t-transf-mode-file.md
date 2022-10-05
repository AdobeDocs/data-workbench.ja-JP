---
description: 設定ファイル Transform Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。変換機能を実行する Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。
title: Transform Mode.cfg ファイル
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 74%

---

# Transform Mode.cfg ファイル{#the-transform-mode-cfg-file}

{{eol}}

設定ファイル Transform Mode.cfg では、データセットに組み入れるデータの処理を一時停止したり、オフラインソースを指定したりすることができます。変換機能を実行する Data Workbench サーバーの状態ファイルが保存される頻度を指定することもできます。

ソースの追加と削除を含め、[!DNL Transform Mode.cfg] ファイルに変更を加えても、データの再処理は行われません。

**データセットプロファイルの Transform Mode.cfg ファイルを編集するには**

1. データのエクスポートを行うプロファイル内で、 [!DNL Profile Manager] をクリックし、 **[!UICONTROL Dataset]** ディレクトリの内容を表示します。
1. の横のチェックマークを右クリックします。 [!DNL Transform Mode.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. この [!DNL Transform Mode.cfg] ウィンドウが表示されます。
1. 次の表を参考にして、設定ファイルのパラメーターを編集します。

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> パラメーター </th> 
    <th colname="col2" class="entry"> 説明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Offline Sources </td> 
    <td colname="col2"> <p>オフラインログソースのマスク。 </p> <p> オフラインソースを指定するには： </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> <span class="uicontrol">Offline Sources</span> を右クリックし、<span class="uicontrol">新規追加</span>／<span class="uicontrol">Source</span> をクリックします。 </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 新しいソースのパラメーターに、ログシーケンスのマスクを入力します。ファイル名が <span class="filepath">YYYYMMDD-SENSORID.vsl</span> 形式の Sensor ログソースの場合、マスクは <i>SENSORID</i> です。SENSORID の大文字と小文字は区別されます。ログファイルログソースの場合、マスクは <span class="wintitle"> マスクパターン</span> ( <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> ログファイル</a>) をクリックします。 </li> 
    </ul> <p> <span class="wintitle">Offline Sources</span> に属しているソースは、追加したり削除したりしても、データセットの再処理は実行されません。 </p> <p> 基準日時の測定は、プロファイルのオンラインソースの処理に対して維持されます。オフラインソースが再びオンラインになると、そのソースから送られてくるログファイルの処理が再開されます。 </p> <p> <p>注意：ソースがオンラインに戻ったらすぐに、<span class="wintitle">Offline Sources</span> からそのソースを削除する必要があります。削除しなかった場合、Data Workbench サーバーは、ソースからデータが送信されている限り、そのソースをオンラインソースとして処理し、基準日時を更新します。そのソースが再度オフラインになった場合、基準日時の測定が停止します。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Paused </td> 
    <td colname="col2"> true または false。true の場合、新しいデータは処理されず、データセットに追加されません。デフォルト値は false です。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Save Interval (sec) </td> 
    <td colname="col2"> <p>変換機能が実行されている Data Workbench サーバーでその状態ファイルが保存される頻度。デフォルト値は 3600 です。 </p> <p> <p>注意：変更が必要な場合は必ずアドビまでご相談ください。 </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Data Workbench ウィンドウ内で [!DNL Transform Mode.cfg] ファイルを編集するときは、基本的な編集機能にショートカットキーを使用できます。切り取り（Ctrl + X）、コピー（Ctrl + C）、貼り付け（Ctrl + V）、取り消し（Ctrl + Z）、やり直し（Ctrl + Shift + Z）、セクション選択（クリックしながらドラッグ）、すべて選択（Ctrl + A）などの操作が可能です。また、ショートカットを使用して、1 つの設定ファイル ( [!DNL .cfg]) を別のに置き換えます。

1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. ローカルで行った変更を有効にするには、 [!DNL Profile Manager]、 data workbench のチェックマークを右クリックします。 [!DNL Transform Mode.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > **[!UICONTROL profile name]**（ profile name は、データをエクスポートするプロファイルの名前） プロファイルの同期後、データの再処理が開始されます。

   エクスポートするデータの再処理について詳しくは、 [再処理と再変換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
