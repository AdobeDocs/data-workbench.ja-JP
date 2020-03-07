---
description: Insightサーバーのシステムイベントメッセージを追跡するには、イベントログファイルを定期的に監視する必要があります。このメッセージは、Insightサーバーのインストールディレクトリ内のEventsフォルダーにある<YYYYMMDD>-event.txtファイルにデフォルトで記録されます。
solution: Insight
title: 管理イベントの監視
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理イベントの監視{#monitoring-administrative-events}

イベントログファイルを定期的に監視して、Insight Serverシステムのイベントメッセージを追跡する必要があります。このメッセージは、Insight Serverのインストールディレクトリ内のEventsフォルダーにあるデフォルトのファイルに記録されます。 `<YYYYMMDD>-event.txt`

**推奨頻度：** 5 ～ 10分ごと

これらのイベントは、 [!DNL Server Files Manager] in 、自動管理ツ [!DNL Insight]ール、ファイル、またはWindowsイベ [!DNL *-event.txt] ントビューアを使用して監視できます。

>[!NOTE]
>
>管理イベントログは、Windowsイベントログとは完全に異なりますが、同じイベントの一部が含まれています。 管理イベントログには、イベントに関する情報のみが含ま [!DNL Insight Server] れます。

**events.txtファイルを[!DNL Server Files Manager]**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. アクティブなアイコンを右クリックし、を [!DNL Insight Server] クリックしま **[!UICONTROL Server Files]**&#x200B;す。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Events]** to view its contents.
1. 目的のファイルの横にあるサーバー名 *列のチェック* マークを右クリックし、をクリックしま **[!UICONTROL Make Local]**&#x200B;す。 列内のファイル名の横にチェックマークが表示され [!DNL Temp] ます。
1. 列のチェックマークを右クリックし、/ [!DNL Temp] をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL in Notepad]**&#x200B;す。 イベントファイルは、Microsoft Windowsのメモ帳の新しいウィンドウに表示されます。

   ![ステップ情報](assets/vis_FileManager_eventfile.png)

   インス [!DNL Server.log] トールディレクトリ内 [!DNL Trace] のフォルダー内のフ [!DNL Insight Server] ァイルに、より詳細なログ情報が含まれています。

**Windowsイベントビューアでイベントを表示するには**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**管理イベントログディレクトリを変更するには**

管理イベントログの設定ファイルでは、 [!DNL Administrative Events Log.cfg]イベントログの出力先ディレクトリを指定します。

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。

1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Administrative Event Logs.cfg] ファイルは、このディレクトリ内に格納されています。

1. Right-click the check mark in the *server name* column for [!DNL Administrative Event Logs.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Administrative Event Logs.cfg].

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. In the [!DNL Administrative Event Logs.cfg] window, click **[!UICONTROL component]** to view its contents. デフォルトのパスは、インスト [!DNL Events] ールディレクトリ内の [!DNL Insight Server] フォルダーです。

   ![](assets/cfg_adminevents_examplevalues.png)

1. Pathパラメーターに、イベントログデータを出力するディレクトリの名前を入力します。
1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし、 [!DNL Temp] /を選択 **[!UICONTROL Save to]** します **[!UICONTROL server name]**。

