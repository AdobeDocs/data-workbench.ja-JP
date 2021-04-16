---
description: イベントログファイルを定期的に監視し、Insight Serverのシステムイベントメッセージを追跡する必要があります。このメッセージは、デフォルトで、Insight Serverのインストールディレクトリ内のイベントフォルダーにある<YYYYMMDD>-イベント.txtファイルに記録されます。
title: 管理イベントの監視
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 3%

---

# 管理イベントの監視{#monitoring-administrative-events}

Insight Serverのイベントイベントメッセージを追跡するには、イベントログファイルを定期的に監視する必要があります。このメッセージは、Insight Serverのインストールディレクトリ内のフォルダーにある`<YYYYMMDD>-event.txt`ファイルにデフォルトで記録されます。

**推奨頻度：5 ～ 10分** ごと

[!DNL Insight]の[!DNL Server Files Manager]、自動管理ツール、[!DNL *-event.txt]ファイル、またはWindowsイベントビューアを使用して、これらのイベントを監視できます。

>[!NOTE]
>
>管理イベントログは、Windowsイベントログとは完全に別のものですが、同じイベントがいくつか含まれています。 管理イベントログには、[!DNL Insight Server]イベントに関する情報のみが含まれます。

**イベント.txtファイルを[!DNL Server Files Manager]**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. アクティブな[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。
1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Events]**&#x200B;をクリックして、内容を表示します。
1. 目的のファイルの横の&#x200B;*server name*&#x200B;列のチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。 [!DNL Temp]列のファイル名の横にチェックマークが表示されます。
1. [!DNL Temp]列のチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。 イベントファイルが新しいMicrosoft Windowsのメモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/vis_FileManager_eventfile.png)

   [!DNL Insight Server]インストールディレクトリ内の[!DNL Trace]フォルダー内の[!DNL Server.log]ファイルには、より詳細なログ情報が含まれています。

**WindowsイベントViewerでイベントを表示するには**

* **[!UICONTROL Start]**/**[!UICONTROL Control Panel]**/**[!UICONTROL Administrative Tools]**/**[!UICONTROL Event Viewer]**&#x200B;をクリックします。

**管理イベントログディレクトリを変更するには**

管理イベントログの設定ファイル[!DNL Administrative Events Log.cfg]は、イベントログの出力先ディレクトリを指定します。

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。

1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。

1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components]**&#x200B;をクリックして、内容を表示します。 [!DNL Administrative Event Logs.cfg] ファイルは、このディレクトリ内に格納されています。

1. [!DNL Administrative Event Logs.cfg]の&#x200B;*サーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Administrative Event Logs.cfg]の[!DNL Temp]列にチェックマークが表示されます。

1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。

1. [!DNL Administrative Event Logs.cfg]ウィンドウで、**[!UICONTROL component]**&#x200B;をクリックして内容を表示します。 デフォルトのパスは、[!DNL Insight Server]インストールディレクトリ内の[!DNL Events]フォルダーです。

   ![](assets/cfg_adminevents_examplevalues.png)

1. Pathパラメーターに、イベントログデータを出力するディレクトリの名前を入力します。
1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/**[!UICONTROL server name]**&#x200B;を選択します。
