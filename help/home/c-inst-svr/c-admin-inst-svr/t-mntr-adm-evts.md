---
description: イベントログファイルを定期的に監視して、Insight サーバーのシステムイベントメッセージを追跡する必要があります。このメッセージは、 <yyyymmdd>-event.txt ファイルは、Insight サーバーのインストールディレクトリ内の Events フォルダーにデフォルトで配置されています。
title: 管理イベントの監視（Insight サーバー）
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# 管理イベントの監視{#monitoring-administrative-events}

イベントログファイルを定期的に監視して、Insight サーバーのシステムイベントメッセージを追跡する必要があります。このメッセージは、 `<YYYYMMDD>-event.txt` デフォルトで、Insight サーバーのインストールディレクトリ内の Events フォルダーにあるファイル。

**推奨頻度：** 5 ～ 10 分ごと

これらのイベントは、 [!DNL Server Files Manager] in [!DNL Insight]、自動管理ツール、 [!DNL *-event.txt] ファイル、または Windows イベントビューア

>[!NOTE]
>
>管理イベントログは、Windows イベントログとは完全に別のものですが、同じイベントの一部が含まれています。 管理イベントログには、 [!DNL Insight Server] イベント。

**events.txt ファイルを[!DNL Server Files Manager]**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. アクティブな [!DNL Insight Server] をクリックし、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Events]** をクリックして、その内容を表示します。
1. チェックマーク ( *サーバー名* 列をクリックし、 **[!UICONTROL Make Local]**. ファイル名の横に、 [!DNL Temp] 列。
1. チェックマーク ( [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 新しいMicrosoft Windows メモ帳ウィンドウにイベントファイルが表示されます。

   ![ステップ情報](assets/vis_FileManager_eventfile.png)

   この [!DNL Server.log] ファイルを [!DNL Trace] フォルダー内の [!DNL Insight Server] インストールディレクトリには、より詳細なログ情報が含まれています。

**Windows イベントビューアでイベントを表示するには**

* クリック **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**管理イベントログディレクトリを変更するには**

管理イベントログの設定ファイル [!DNL Administrative Events Log.cfg]：イベントログを出力するディレクトリを指定します。

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。

1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.

1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Administrative Event Logs.cfg] ファイルは、このディレクトリ内に格納されています。

1. チェックマーク ( *サーバー名* 列 [!DNL Administrative Event Logs.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Administrative Event Logs.cfg].

1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 内 [!DNL Administrative Event Logs.cfg] ウィンドウ、クリック **[!UICONTROL component]** をクリックして、その内容を表示します。 デフォルトのパスは [!DNL Events] フォルダー内の [!DNL Insight Server] インストールディレクトリ。

   ![](assets/cfg_adminevents_examplevalues.png)

1. Path パラメーターに、イベントログデータを出力するディレクトリの名前を入力します。
1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
