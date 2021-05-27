---
description: イベントデータ領域の監視とSensorデータのログディレクトリの変更に関する情報です。
title: イベントデータ容量の監視
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---

# イベントデータ容量の監視{#monitoring-event-data-space}

イベントデータ領域の監視とSensorデータのログディレクトリの変更に関する情報です。

**推奨頻度：** 5 ～ 10分ごと

[!DNL Insight Server] では、設定に応じ [!DNL Sensor] て、データ処理ユニットまたはファイルサーバーユニットで1日に1つのログファイルを保存します。ログファイルのサイズとログファイルに必要なデータストレージ領域の量は、ログに記録されるWebサイトの数やWebサーバーが1秒あたりに受け取る要求の数など、多くの変数によって異なります。

[!DNL Insight Server] （または[!DNL Insight Server]クラスタ）の一般的なインストールでは、複数のテラバイトのデータを格納できます(実装では、[!DNL Insight Server]マシンのAdobeで推奨されるハードウェアが使用される場合)。

通常、すべてのログデータは[!DNL Insight Server]マシンに残ります。 マシン上で利用可能なデータストレージ領域を増やす必要が生じた場合は、最新のログファイル以外のすべてのログファイルを別のマシンまたはデータストレージメディア（zipドライブ、テープなど）に移動できます。 データを移動する際に[!DNL Insight Server]を停止する必要はなく、[!DNL Insight Server]に接続され、連続データを使用する[!DNL Insights]で使用できる機能には影響しません。 分析データセットを処理または再処理しない場合、以前のすべてのデータへのアクセス権が維持され、新しいデータは引き続き[!DNL Insight]で使用できます。 分析データセットを処理または再処理する場合は、処理が完了するまでデータにアクセスできません。

デフォルトでは、[!DNL Sensor]によって生成され[!DNL Insight Server]に送信されるイベントデータは、[!DNL Insight Server]インストールディレクトリ内の[!DNL Logs]フォルダーに保存されます。 通信設定ファイル[!DNL Communications.cfg]は、[!DNL Insight Server]が読み取るイベントデータログファイルの場所を指定します。

**データのログディレクトリを変更する [!DNL Sensor] には**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. *[!DNL Communications.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Communications.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL Communications.cfg]ウィンドウで、「**[!UICONTROL component]**」をクリックして内容を表示します。
1. [!DNL Communications.cfg]ウィンドウで、「**[!UICONTROL Servers]**」をクリックして内容を表示します。 複数のタイプのサーバーが表示される場合があります。ファイル・サーバ、ログ・サーバ、Initサーバ、ステータス・サーバ、送信サーバ、レプリケート・サーバ。
1. [!DNL Sensor]が処理するログファイルを書き込むLoggingServer （[!DNL Insight Server]によって処理されるログファイル）を探し、その番号をクリックしてメニューを表示します。

   ![ステップ情報](assets/cfg_communications_examplevalues_logging.png)

   デフォルトのログディレクトリは、[!DNL Insight Server]インストールディレクトリ内の[!DNL Logs]フォルダーです。

1. Log Directory パラメーターを編集して、ログファイルの適切な場所を反映します。

   >[!NOTE]
   >
   >LoggingServer のパラメーター以外は編集しないでください。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   複数のFileServerが「サーバー」ノードの下に表示される場合があるので、変更するLogs\のローカルパスを持つサーバーを見つけるには、それらの内容を（[!DNL Servers]リスト内の数字をクリックして）表示する必要があります。

1. [!DNL .vsl]ファイルの目的の場所を反映するようにローカルパスを編集します。

   >[!NOTE]
   >
   >FileServerの他のパラメータは変更しないでください。

   ログファイルの場所は[!DNL Communications.cfg]ファイル内で変更されていますが、FileServerのURIとして/Logs/を指定することで、これらのファイルを[!DNL Server Files Manager]のLogsディレクトリにマッピングできます。

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;を選択します。
