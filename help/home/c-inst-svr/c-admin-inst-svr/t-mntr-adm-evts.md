---
description: イベントログファイルを定期的に監視し、Insight Serverのシステムイベントメッセージを追跡する必要があります。このメッセージは、デフォルトで、Insight Serverのインストールディレクトリ内のイベントフォルダーにある<YYYYMMDD>-イベント.txtファイルに記録されます。
solution: Analytics
title: 管理イベントの監視
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 3%

---


# 管理イベントの監視{#monitoring-administrative-events}

Insight Serverのイベントイベントメッセージを追跡するには、イベントログファイルを定期的に監視する必要があります。このメッセージは、Insight Serverのインストールディレクトリ内のフォルダーにあるデフォルトのファイルに記録されます。 `<YYYYMMDD>-event.txt`

**推奨頻度：** 5 ～ 10分ごと

これらのイベントは、 [!DNL Server Files Manager] in、automated managementツール、 [!DNL Insight][!DNL *-event.txt] ファイル、またはWindowsイベントビューアを使用して監視できます。

>[!NOTE]
>
>管理イベントログは、Windowsイベントログとは完全に別のものですが、同じイベントがいくつか含まれています。 管理イベントログには、 [!DNL Insight Server] イベントに関する情報のみが含まれます。

**イベント.txtファイルを[!DNL Server Files Manager]**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. アクティブなアイコンを右クリックし、 [!DNL Insight Server] をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Events]** to view its contents.
1. 目的のファイルの横にある *サーバー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 列のファイル名の横にチェックマークが表示され [!DNL Temp] ます。
1. 列のチェックマークを右クリックし、 [!DNL Temp] 「>」をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Notepad]**&#x200B;す。 イベントファイルが新しいMicrosoft Windowsのメモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/vis_FileManager_eventfile.png)

   インストー [!DNL Server.log] ルディレクトリ内の [!DNL Trace][!DNL Insight Server] フォルダー内のファイルには、より詳細なログ情報が含まれています。

**WindowsイベントViewerでイベントを表示するには**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**管理イベントログディレクトリを変更するには**

管理イベントログ設定ファイル [!DNL Administrative Events Log.cfg]は、イベントログの出力先ディレクトリを指定します。

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。

1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Administrative Event Logs.cfg] ファイルは、このディレクトリ内に格納されています。

1. Right-click the check mark in the *server name* column for [!DNL Administrative Event Logs.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Administrative Event Logs.cfg].

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. In the [!DNL Administrative Event Logs.cfg] window, click **[!UICONTROL component]** to view its contents. デフォルトのパスは、インストー [!DNL Events][!DNL Insight Server] ルディレクトリ内のフォルダーです。

   ![](assets/cfg_adminevents_examplevalues.png)

1. Pathパラメーターに、イベントログデータを出力するディレクトリの名前を入力します。
1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。
   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] /を選択し **[!UICONTROL Save to]** ま **[!UICONTROL server name]**&#x200B;す。

