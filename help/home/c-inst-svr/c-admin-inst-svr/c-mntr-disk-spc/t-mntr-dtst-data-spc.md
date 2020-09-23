---
description: データセットの監視と、データセットデータストレージの新しい場所の追加について取り上げます。
solution: Analytics
title: データセットデータ容量の監視
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---


# データセットデータ容量の監視{#monitoring-dataset-data-space}

データセットの監視と、データセットデータストレージの新しい場所の追加について取り上げます。

**推奨頻度：** 5 ～ 10分ごと

デフォルトでは、はデータ処理ユニット上の [!DNL Insight Server] プログラムファイルと同じドライブ上の [!DNL temp.db][!DNL Insight Server] ファイルにデータセットを書き込みます。 1台のコン [!DNL Insight Server] ピューターあたりのデータセットデータの量は、次のいずれかに制限されます。

* そのデータセットへのデータ入力の5億（5億）万件のレコード
* 500 GBのデータセットデータが保存される
* ルートレベルの任意のディメンションごとに1 MBのデータセットデータが格納される(例えば、1訪問者あたり5,000個のレコード、レコードあたり平均200バイト)

データセットを別のドライブに維持する [!DNL Insight Server] 場合、または収集するデータ量に複数のドライブを使用する必要がある場合は、ディスクファイル構成ファイル( [!DNL Disk Files.cfg])を更新し、ファイル [!DNL Insight Server][!DNL temp.db] の書き込み先を指定する必要があります。 この [!DNL Disk Files.cfg] ファイルには、ディスクファイル（文字列ベクトル）がリストされ、再処理と操作の [!DNL Insight Server] 間に使用されるデータセットデータの場所が指定されます。 通常、物理ドライブあたり1つのファイルが存在します。

>[!NOTE]
>
>ファイルの内容がインストール中に変更された可能性があり [!DNL Disk Files.cfg][!DNL Insight Server]ます。 詳しくは、「データセットの場所の [設定(temp.db)」を参照してください](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)。

**データセットデータストレージの新しい場所を追加するには**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Disk Files.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Disk Files.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Disk Files.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Disk Files.cfg] window, click **[!UICONTROL component]** to view its contents.

   ![ステップ情報](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、ディスクアクセス速度の向上に [!DNL Insight Server] 使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのパラメーターを変更する前に、Adobeにお問い合わせください。

1. マシン上のディスクファイルを変更するには、 [!DNL Insight Server] 右クリックし **[!UICONTROL Disk Files]** て **[!UICONTROL Add new]** >をクリックし **[!UICONTROL Disk File]**&#x200B;ます。

   ディスクファイルを削除するには、ディスクファイル番号を右クリックし、をクリックし **[!UICONTROL Remove]**&#x200B;ます。

1. 新しいディスクファイルの場合は、再処理中や操作中に使用するファイルのディレクトリと名前 [!DNL Insight Server] を入力します。

   ![ステップ情報](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、ディスクアクセス速度の向上に [!DNL Insight Server] 使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのパラメーターを変更する前に、Adobeにお問い合わせください。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

