---
description: イベントデータ領域の監視と、Sensorデータのログディレクトリの変更に関する情報です。
solution: Insight
title: イベントデータ領域の監視
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# イベントデータ領域の監視{#monitoring-event-data-space}

イベントデータ領域の監視と、Sensorデータのログディレクトリの変更に関する情報です。

**推奨頻度：** 5 ～ 10分ごと

[!DNL Insight Server] は、設定に応じて、1日 [!DNL Sensor] に1つのログファイルをデータ処理ユニットまたはファイルサーバーユニットに保存します。 ログファイルのサイズとログファイルに必要なデータ保存領域の量は、ログに記録されるWebサイトの数やWebサーバーが1秒間に受け取る要求の数など、多くの変数によって異なります。

通常の(またはクラ [!DNL Insight Server] スター [!DNL Insight Server] )のインストールでは、複数のテラバイトのデータを格納できます。導入でアドビが推奨するハードウェアがマシンに使用されてい [!DNL Insight Server] ると仮定します。

通常、すべてのログデータはコンピューター上に残 [!DNL Insight Server] ります。 マシン上で使用可能なデータ記憶領域を増やす必要が生じた場合は、最新日のログファイル以外のすべてのログファイルを別のマシンまたはデータ記憶媒体（zipドライブ、テープなど）に移動できます。 データの移動を停止する必要はなく、連続デ [!DNL Insight Server]ータに接続され、連続データを使用して作業する場合 [!DNL Insights] に使用できる機能に [!DNL Insight Server] は影響を与えません。 分析データセットを処理または再処理しない場合、以前のすべてのデータへのアクセス権を保持し、で引き続き新しいデータを使用できま [!DNL Insight]す。 分析データセットを処理または再処理する場合、処理が完了するまでデータにアクセスできません。

デフォルトでは、によって生成され、に送信さ [!DNL Sensor] れるイベントデ [!DNL Insight Server] ータは、インストールディレクトリ内 [!DNL Logs] のフォルダに [!DNL Insight Server] 格納されます。 Communications設定ファイルは、読み [!DNL Communications.cfg]取り元のイベントデータログファイルの場所を指定しま [!DNL Insight Server]す。

**データのログディレクトリを変更する[!DNL Sensor]には**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Communications.cfg] window, click **[!UICONTROL component]** to view its contents.
1. In the [!DNL Communications.cfg] window, click **[!UICONTROL Servers]** to view its contents. 次のような複数の種類のサーバが表示されます。ファイルサーバー、ログサーバー、Initサーバー、ステータスサーバー、送信サーバー、複製サーバー。
1. LoggingServer(処理対象のログファ [!DNL Sensor] イルを書き込む場所)を探し、その [!DNL Insight Server]番号をクリックしてメニューを表示します。

   ![ステップ情報](assets/cfg_communications_examplevalues_logging.png)

   The default log directory is the [!DNL Logs] folder within the [!DNL Insight Server] installation directory.

1. Log Directory パラメーターを編集して、ログファイルの適切な場所を反映します。

   >[!NOTE]
   >
   >LoggingServer のパラメーター以外は編集しないでください。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   サーバーノードの下に複数のFileServerが表示される場合があるので、変更するログのローカルパスを持つサーバーを見つけるには、その多くのFileServerの内容を(リスト内の数字をクリックして [!DNL Servers] )表示する必要があります。

1. ローカルパスを編集して、ファイルの目的の場所を反映し [!DNL .vsl] ます。

   >[!NOTE]
   >
   >FileServerのその他のパラメーターは変更しないでください。

   ログファイルの場所は変更されましたが、 [!DNL Communications.cfg] /Logs/をFileServerのURIとして指定することで、これらのファイルをのLogsディレ [!DNL Server Files Manager] クトリにマッピングできます。

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

