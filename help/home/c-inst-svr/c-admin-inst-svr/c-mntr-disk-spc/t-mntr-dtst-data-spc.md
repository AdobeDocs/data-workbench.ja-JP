---
description: データセットの監視と、データセットデータストレージの新しい場所の追加に関する情報です。
title: データセットデータ容量の監視
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 4%

---

# データセットデータ容量の監視{#monitoring-dataset-data-space}

{{eol}}

データセットの監視と、データセットデータストレージの新しい場所の追加に関する情報です。

**推奨頻度：** 5 ～ 10 分ごと

デフォルトでは、 [!DNL Insight Server] データセットをに書き込みます。 [!DNL temp.db] ファイルを [!DNL Insight Server] プログラムファイルを Data Processing Unit に保存します。 1 回のデータセットデータの量 [!DNL Insight Server] マシンは次のいずれかに制限されます。

* そのデータセットに入力されたデータの 5 億（5 億）のレコード
* 500 GB のデータセットデータを保存
* 1 つのルートレベルディメンションごとに 1 MB のデータセットデータ（例：訪問者あたり 5,000 件のレコード、平均 200 バイト/レコード）が保存されます。

必要に応じて [!DNL Insight Server] 別のドライブにデータセットを維持する場合、または収集するデータの量に複数のドライブを使用する必要がある場合は、ディスクファイル構成ファイル ( [!DNL Disk Files.cfg]) をクリックし、必要な場所を指定します。 [!DNL Insight Server] 書く [!DNL temp.db] ファイルに含まれています。 この [!DNL Disk Files.cfg] ファイルには、ディスクファイル（文字列ベクトル）がリストされ、 [!DNL Insight Server] 再処理中および操作中。 通常、物理ドライブごとに 1 ファイルが存在します。

>[!NOTE]
>
>の内容 [!DNL Disk Files.cfg] インストール中にファイルが変更された可能性があります [!DNL Insight Server]. 詳しくは、 [データセット (temp.db) の場所の設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**データセットデータストレージの新しい場所を追加するには**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Disk Files.cfg] ファイルは、このディレクトリ内に格納されています。
1. チェックマーク ( *サーバー名* 列 [!DNL Disk Files.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Disk Files.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 内 [!DNL Disk Files.cfg] ウィンドウ、クリック **[!UICONTROL component]** をクリックして、その内容を表示します。

   ![ステップ情報](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >Detect Disk Corruption パラメーターは、デフォルトで true に設定されています。 Disk Cache Size (MB) パラメータは、 [!DNL Insight Server] はを使用してディスクアクセス速度を上げ、デフォルトでは 128 に設定されています。 これらのAdobeを変更する前に、パラメータに連絡してください。

1. 上のディスクファイルを変更するには [!DNL Insight Server] マシン、右クリック **[!UICONTROL Disk Files]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   ディスクファイルを削除するには、ディスクファイル番号を右クリックし、 **[!UICONTROL Remove]**.

1. 新しいディスクファイルに対して、使用するファイルのディレクトリと名前を入力します。 [!DNL Insight Server] 再処理中および操作中。

   ![ステップ情報](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >Detect Disk Corruption パラメーターは、デフォルトで true に設定されています。 Disk Cache Size (MB) パラメータは、 [!DNL Insight Server] はを使用してディスクアクセス速度を上げ、デフォルトでは 128 に設定されています。 これらのAdobeを変更する前に、パラメータに連絡してください。

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
