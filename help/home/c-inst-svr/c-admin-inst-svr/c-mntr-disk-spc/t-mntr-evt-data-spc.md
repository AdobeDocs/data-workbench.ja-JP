---
description: イベントのデータ領域の監視とSensorデータのログディレクトリの変更に関する情報です。
solution: Analytics
title: イベントデータ容量の監視
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---


# イベントデータ容量の監視{#monitoring-event-data-space}

イベントのデータ領域の監視とSensorデータのログディレクトリの変更に関する情報です。

**推奨頻度：** 5 ～ 10分ごと

[!DNL Insight Server] では、設定に応じて、1日 [!DNL Sensor] に1つのログファイルをデータ処理ユニットまたはファイルサーバーユニットに保存します。 ログファイルのサイズとログファイルに必要なデータストレージ領域の量は、ログに記録されるWebサイトの数や1秒あたりに受け取る要求の数など、多くの変数によって異なります。

（またはクラスタ）の一般的なインストール [!DNL Insight Server] では、複数のテラバイトのデータを格納できます。実装では、 [!DNL Insight Server][!DNL Insight Server] マシンのAdobeが推奨するハードウェアが使用されると仮定します。

通常、すべてのログデータは [!DNL Insight Server] マシン上に残ります。 コンピューター上で使用可能なデータストレージ領域を増やす必要が生じた場合は、最新のログファイル以外のすべてのログファイルを別のコンピューターまたはデータストレージ媒体（zipドライブ、テープなど）に移動できます。 データを移動する際に停止する必要はありません。また、連続データに接続し [!DNL Insight Server]て作業している場合でも、データを移動しても機能に影響を与えるこ [!DNL Insights][!DNL Insight Server] とはありません。 分析データセットを処理または再処理しない場合、以前のすべてのデータへのアクセスを維持し、で引き続き新しいデータを使用でき [!DNL Insight]ます。 分析データセットを処理または再処理する場合、処理が完了するまでデータにアクセスできません。

デフォルトでは、によって生成され、に送信され [!DNL Sensor] たイベントデータは、インストー [!DNL Insight Server] ルディレクトリ内 [!DNL Logs][!DNL Insight Server] のフォルダに格納されます。 Communications構成ファイル [!DNL Communications.cfg]は、読み取り元のイベントデータログファイルの場所を指定し [!DNL Insight Server]ます。

**データのログディレクトリを変更するには[!DNL Sensor]**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Communications.cfg] window, click **[!UICONTROL component]** to view its contents.
1. In the [!DNL Communications.cfg] window, click **[!UICONTROL Servers]** to view its contents. 次のような種類のサーバが表示されます。ファイルサーバー、ログサーバー、Initサーバー、ステータスサーバー、送信サーバー、または複製サーバー。
1. LoggingServer(処理対象のログファイルを [!DNL Sensor] 書き込む場所)を探し、その番号をクリックし [!DNL Insight Server]てメニューを表示します。

   ![ステップ情報](assets/cfg_communications_examplevalues_logging.png)

   The default log directory is the [!DNL Logs] folder within the [!DNL Insight Server] installation directory.

1. Log Directory パラメーターを編集して、ログファイルの適切な場所を反映します。

   >[!NOTE]
   >
   >LoggingServer のパラメーター以外は編集しないでください。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   サーバーノードには複数のFileServerが表示される場合があるので、変更するログのローカルパスを持つサーバーを見つけるには、その内容を( [!DNL Servers] リスト内で数字をクリックして)表示する必要がある場合があります。

1. ローカルパスを編集して、 [!DNL .vsl] ファイルの場所を反映します。

   >[!NOTE]
   >
   >FileServerのその他のパラメーターは変更しないでください。

   ログファイル内のログファイルの場所は変更されていますが、FileServerのURIとして/Logs/を指定することで、これらのファイルを [!DNL Communications.cfg][!DNL Server Files Manager] のLogsディレクトリにマッピングできます。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

