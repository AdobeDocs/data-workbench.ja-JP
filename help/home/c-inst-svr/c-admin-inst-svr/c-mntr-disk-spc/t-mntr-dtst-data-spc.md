---
description: データセットデータストレージのデータセット監視と新しい場所の追加に関する情報です。
solution: Insight
title: データセットデータ領域の監視
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データセットデータ領域の監視{#monitoring-dataset-data-space}

データセットデータストレージのデータセット監視と新しい場所の追加に関する情報です。

**推奨頻度：** 5 ～ 10分ごと

デフォルトでは、 [!DNL Insight Server] データ処理ユニット上のプ [!DNL temp.db] ログラムファイルと同じドライブ上のフ [!DNL Insight Server] ァイルにデータセットが書き込まれます。 1台あたりのデータセットデータの量 [!DNL Insight Server] は、次のいずれかの方法に制限されます。

* そのデータセットへのデータ入力が5億件（5億件）に上る
* 500 GBのデータセットデータが保存される
* 任意の1つのルートレベルディメンションに1 MBのデータセットデータが格納されます（例えば、訪問者あたり平均200バイトの5,000レコードが1レコードあたりに格納されます）。

データセット [!DNL Insight Server] を別のドライブに保持する場合や、収集するデータの量が複数のドライブの使用を必要とする場合は、ディスクファイル構成ファイル( [!DNL Disk Files.cfg])を更新して、ファイルの書き込み先を指定する必要があり [!DNL Insight Server][!DNL temp.db] ます。 このフ [!DNL Disk Files.cfg] ァイルには、ディスクファイル（文字列ベクトル）が一覧表示され、再処理および操作時に使用されるデータセットデ [!DNL Insight Server] ータの場所が指定されます。 通常、物理ドライブあたり1つのファイルが存在します。

>[!NOTE]
>
>ファイルの内容がインスト [!DNL Disk Files.cfg] ール中に変更された可能性がありま [!DNL Insight Server]す。 詳しくは、「データセ [ットの場所の設定(temp.db)」を参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。

**データセットデータストレージの新しい場所を追加するには**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Disk Files.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Disk Files.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Disk Files.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Disk Files.cfg] window, click **[!UICONTROL component]** to view its contents.

   ![ステップ情報](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、ディスクアクセス速度の向上に使用するメ [!DNL Insight Server] モリの量を制御し、デフォルトでは128に設定されます。 これらのパラメーターのいずれかを変更する前に、アドビにお問い合わせください。

1. マシン上のディスクファイルを変更す [!DNL Insight Server] るには、右クリックし、 **[!UICONTROL Disk Files]** >をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Disk File]**&#x200B;す。

   ディスクファイルを削除するには、ディスクファイル番号を右クリックし、をクリックしま **[!UICONTROL Remove]**&#x200B;す。

1. 新しいディスクファイルの場合は、再処理と操作時に使用するファイルのディレクトリと [!DNL Insight Server] 名前を入力します。

   ![ステップ情報](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、ディスクアクセス速度の向上に使用するメ [!DNL Insight Server] モリの量を制御し、デフォルトでは128に設定されます。 これらのパラメーターのいずれかを変更する前に、アドビにお問い合わせください。

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

