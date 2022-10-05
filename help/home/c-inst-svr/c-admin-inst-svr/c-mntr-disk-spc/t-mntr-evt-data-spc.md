---
description: イベントデータ領域の監視と Sensor データのログディレクトリの変更に関する情報です。
title: イベントデータ容量の監視
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---

# イベントデータ容量の監視{#monitoring-event-data-space}

{{eol}}

イベントデータ領域の監視と Sensor データのログディレクトリの変更に関する情報です。

**推奨頻度：** 5 ～ 10 分ごと

[!DNL Insight Server] 次のログファイルを 1 つ格納 [!DNL Sensor] 設定に応じて、データ処理ユニットまたはファイルサーバーユニットの 1 日あたり。 ログファイルのサイズとログファイルに必要なデータストレージ容量は、ログに記録される Web サイトの数や Web サーバーが 1 秒あたりに受け取る要求の数など、多くの変数によって異なります。

の一般的なインストール [!DNL Insight Server] ( または [!DNL Insight Server] （クラスタ）は、実装でAdobeが推奨するハードウェアを使用していると仮定して、複数のテラバイトのデータを保存できます [!DNL Insight Server] マシンです。

通常、すべてのログデータは [!DNL Insight Server] マシン。 マシン上でより多くのデータストレージ領域を使用可能にする必要が生じた場合は、最新のログファイル以外のすべてのログファイルを別のマシンまたはデータストレージメディア（zip ドライブ、テープなど）に移動できます。 データの移動を停止する必要はありません [!DNL Insight Server]また、 [!DNL Insights] それが [!DNL Insight Server] 継続的なデータを扱う 分析データセットを処理または再処理しない場合、以前のすべてのデータへのアクセス権が保持され、新しいデータは引き続き [!DNL Insight]. 分析データセットを処理または再処理する場合は、処理が完了するまでデータにアクセスできません。

デフォルトでは、 [!DNL Sensor] に送信され、 [!DNL Insight Server] が [!DNL Logs] フォルダー内の [!DNL Insight Server] インストールディレクトリ。 通信設定ファイル [!DNL Communications.cfg]は、が読み取るイベントデータログファイルの場所を指定します。 [!DNL Insight Server].

**のログディレクトリを変更するには [!DNL Sensor] データ**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. チェックマーク ( *サーバー名* 列 [!DNL Communications.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Communications.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 内 [!DNL Communications.cfg] ウィンドウ、クリック **[!UICONTROL component]** をクリックして、その内容を表示します。
1. 内 [!DNL Communications.cfg] ウィンドウ、クリック **[!UICONTROL Servers]** をクリックして、その内容を表示します。 複数のタイプのサーバーが表示される場合があります。ファイルサーバー、ログサーバー、Init サーバー、ステータスサーバー、送信サーバー、またはレプリケートサーバー。
1. LoggingServer ( ) を探します。ここで、 [!DNL Sensor] は処理するログファイルを [!DNL Insight Server]をクリックし、その番号をクリックしてメニューを表示します。

   ![ステップ情報](assets/cfg_communications_examplevalues_logging.png)

   デフォルトのログディレクトリは、 [!DNL Logs] フォルダー内の [!DNL Insight Server] インストールディレクトリ。

1. Log Directory パラメーターを編集して、ログファイルの適切な場所を反映します。

   >[!NOTE]
   >
   >LoggingServer のパラメーター以外は編集しないでください。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   複数の FileServers が [ サーバ ] ノードの下に表示される場合があるので、その多くの FileServer の内容を ( [!DNL Servers] リスト ) をクリックして、変更対象の Logs\のローカルパスを持つサーバを検索します。

1. ローカルパスを編集して、 [!DNL .vsl] ファイル。

   >[!NOTE]
   >
   >FileServer の他のパラメータは変更しないでください。

   ただし、 [!DNL Communications.cfg] ファイルにマッピングする場合、これらのファイルを [!DNL Server Files Manager] /Logs/を FileServer の URI として指定します。

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
