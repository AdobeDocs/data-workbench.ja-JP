---
description: データセットの監視と、データセットデータストレージの新しい場所の追加に関する情報です。
title: データセットデータ容量の監視
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---

# データセットデータ容量の監視{#monitoring-dataset-data-space}

データセットの監視と、データセットデータストレージの新しい場所の追加に関する情報です。

**推奨頻度：** 5 ～ 10分ごと

デフォルトでは、[!DNL Insight Server]はデータ処理ユニット上の[!DNL Insight Server]プログラムファイルと同じドライブ上の[!DNL temp.db]ファイルにデータセットを書き込みます。 [!DNL Insight Server]マシンごとのデータセットデータの量は、次の値に制限されます（いずれか最初に実行する方）。

* そのデータセットに入力されたデータの5億（5億）のレコード
* 500 GBのデータセットデータを保存
* 任意の1つのルートレベルディメンションごとに1 MBのデータセットデータ（例：1レコードあたり平均200バイトの訪問者あたり5,000レコード）

[!DNL Insight Server]でデータセットを別のドライブに維持する場合や、収集するデータ量に複数のドライブを使用する必要がある場合は、[!DNL Insight Server]で[!DNL temp.db]ファイルを書き込む場所を指定するようにディスクファイル設定ファイル([!DNL Disk Files.cfg])を更新する必要があります。 [!DNL Disk Files.cfg]ファイルには、ディスクファイル（文字列ベクトル）が一覧表示され、再処理と操作の際に[!DNL Insight Server]で使用されるデータセットデータの場所が指定されます。 通常、物理ドライブごとに1ファイルが存在します。

>[!NOTE]
>
>[!DNL Disk Files.cfg]ファイルの内容は、[!DNL Insight Server]のインストール中に変更された可能性があります。 詳しくは、[データセット(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)の場所の設定を参照してください。

**データセットデータストレージの新しい場所を追加するには**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Disk Files.cfg] ファイルは、このディレクトリ内に格納されています。
1. *[!DNL Disk Files.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Disk Files.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL Disk Files.cfg]ウィンドウで、「**[!UICONTROL component]**」をクリックして内容を表示します。

   ![ステップ情報](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >デフォルトでは、Detect Disk Corruptionパラメーターはtrueに設定されています。 Disk Cache Size (MB)パラメータは、[!DNL Insight Server]がディスクアクセス速度を上げるために使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのAdobeを変更する前に、パラメーターにお問い合わせください。

1. [!DNL Insight Server]マシン上のディスクファイルを変更するには、**[!UICONTROL Disk Files]**&#x200B;を右クリックし、**[!UICONTROL Add new]** > **[!UICONTROL Disk File]**&#x200B;をクリックします。

   ディスク・ファイルを削除するには、ディスク・ファイル番号を右クリックし、**[!UICONTROL Remove]**&#x200B;をクリックします。

1. 新しいディスクファイルに対して、再処理と操作の際に[!DNL Insight Server]が使用するファイルのディレクトリと名前を入力します。

   ![ステップ情報](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >デフォルトでは、Detect Disk Corruptionパラメーターはtrueに設定されています。 Disk Cache Size (MB)パラメータは、[!DNL Insight Server]がディスクアクセス速度を上げるために使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのAdobeを変更する前に、パラメーターにお問い合わせください。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;を選択します。
