---
description: データセットの監視と、データセットデータストレージの新しい場所の追加について取り上げます。
title: データセットデータ容量の監視
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---

# データセットデータ容量の監視{#monitoring-dataset-data-space}

データセットの監視と、データセットデータストレージの新しい場所の追加について取り上げます。

**推奨頻度：5 ～ 10分** ごと

デフォルトでは、[!DNL Insight Server]はデータ処理ユニットの[!DNL Insight Server]プログラムファイルと同じドライブ上の[!DNL temp.db]ファイルにデータセットを書き込みます。 [!DNL Insight Server]マシンあたりのデータセットデータの量は、次のものに制限されます。

* そのデータセットへのデータ入力の5億（5億）万件のレコード
* 500 GBのデータセットデータが保存される
* ルートレベルの任意のディメンションごとに1 MBのデータセットデータが格納される(例えば、1訪問者あたり5,000個のレコード、レコードあたり平均200バイト)

[!DNL Insight Server]に別のドライブ上のデータセットを維持したい場合や、収集するデータ量が複数のドライブを使用する必要がある場合は、[!DNL Insight Server]に[!DNL temp.db]ファイルを書き込む場所を指定するようにディスクファイル構成ファイル([!DNL Disk Files.cfg])を更新する必要があります。 [!DNL Disk Files.cfg]ファイルは、ディスクファイル（文字列ベクトル）をリストし、再処理と操作中に[!DNL Insight Server]が使用するデータセットデータの場所を指定します。 通常、物理ドライブあたり1つのファイルが存在します。

>[!NOTE]
>
>[!DNL Disk Files.cfg]ファイルの内容は、[!DNL Insight Server]のインストール中に変更された可能性があります。 詳しくは、[データセットの場所の設定(temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e)を参照してください。

**データセットデータストレージの新しい場所を追加するには**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components]**&#x200B;をクリックして、内容を表示します。 [!DNL Disk Files.cfg] ファイルは、このディレクトリ内に格納されています。
1. [!DNL Disk Files.cfg]の&#x200B;*サーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Disk Files.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL Disk Files.cfg]ウィンドウで、**[!UICONTROL component]**&#x200B;をクリックして内容を表示します。

   ![ステップ情報](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、[!DNL Insight Server]がディスクアクセス速度の向上に使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのパラメーターを変更する前に、Adobeにお問い合わせください。

1. [!DNL Insight Server]マシン上のディスクファイルを変更するには、**[!UICONTROL Disk Files]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Disk File]**&#x200B;をクリックします。

   ディスクファイルを削除するには、ディスクファイル番号を右クリックし、**[!UICONTROL Remove]**&#x200B;をクリックします。

1. 新しいディスクファイルには、[!DNL Insight Server]が再処理と操作を行う際に使用するファイルのディレクトリと名前を入力します。

   ![ステップ情報](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Detect Disk Corruptionパラメーターは、デフォルトでtrueに設定されています。 Disk Cache Size (MB)パラメータは、[!DNL Insight Server]がディスクアクセス速度の向上に使用するメモリ量を制御し、デフォルトで128に設定されます。 これらのパラメーターを変更する前に、Adobeにお問い合わせください。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;を選択します。
