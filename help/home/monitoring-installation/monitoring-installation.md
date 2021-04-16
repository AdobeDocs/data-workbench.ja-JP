---
description: Data Workbench監視プロファイルーのインストール手順です。
title: 監視プロファイルのインストール
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# 監視プロファイルのインストール{#installing-the-monitoring-profile}

Data Workbench監視プロファイルーのインストール手順です。

## インストール手順{#section-d4355dbea8a447f48ab168db6ccff612}

1. タグ付きWebページのデータ収集に使用するかのように、新しいSensorインスタンスを設定します。 zig.gifファイルがSensor Webサーバーのドキュメントルートにあることを確認してください。 センサーは、モニタープロファイルと同じホストで実行できます。 （この目的でテキストファイルを使用する場合は問題ありません）。

   >[!NOTE]
   >
   >このSensorインスタンスは、監視エージェントからのトラフィックのみを受信するように専用にする必要があります。 また、このコレクション用のWebサーバーを再利用する場合は、Sensorを別のポートで実行するように設定できます。

1. [!DNL txlogd.conf]ファイルには、次のデフォルト行が含まれています。

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Data Workbench監視プロファイルアプリケーション（または「タグ付き」ページ実装）の場合、GIFファイルを使用して収集するには、イメージタイプを削除する必要があります。 更新された行は次のとおりです。

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. [!DNL insight_monitor.zip/insight_monitor_agent]を一時的な場所にコピーします。
1. 環境用に[!DNL insight_monitor_agent.cfg]ファイルを更新します。 設定ファイル内のコメントに従います。

   **監視設定ファイル：**

   ![](assets/monitor_agent_cfg_sensor.png)

   すべての情報を収集する場所を定義し、URLアドレスを指定します。 これは、専用のセンサーである必要があり、このアプリケーション以外のトラフィックは受信しないでください。

   ![](assets/monitor_agent_cfg_dump.png)

   eがあると仮定したパスがあります。ディスク。 環境のこのパスを変更できます。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Transformプロファイルを実行している場合、Data Workbenchが応答しなくなる可能性があります。 この値を使用すると、プロセスが応答しない状態で3回連続して送信された場合にアラートを送信できます。 これは、偽陽性アラートを減らす方法です。

   ![](assets/monitor_agent_cfg_groups.png)

   ここで、環境ディメンションとグループディメンションを設定します。 これは、ホストごとに異なる場合があります。

   これはw ![](assets/monitor_agent_cfg_debug.png)です。ここでは、このパスのエラー・ログを表示すると、モニタ・エージェントが何をしているかを正確に確認できます。

   ![](assets/monitor_agent_cfg_tempdb.png)

   これは、内部的に一時データベースを使用するためです。 容量に達したときに警告を受ける場合があります。 これは、物理ディスクの使用状況とは異なります。

1. *insight_monitor_agent*&#x200B;フォルダーを、Data Workbenchサーバーを実行する各DPUおよびFSUホストにコピーします。 設定ファイルに示すデフォルトの場所は[!DNL e:\insight_monitor_agent]ですが、この場所は変更できます。

1. 10追加分ごとにエージェントを呼び出すようにWindowsがスケジュールされたタスク（この期間は、処理レートの計算で想定されます）。 プログラムは[!DNL e:insight_monitor/insight_monitor_agent.exe]です。 引数はconfig-file e:\insight_monitor\insight_monitor.cfgです。 e:\insight_monitorの開始。 タスクを実行するユーザーは、[!DNL e:\insight_monitor]の読み取り/書き込みとWin32 OLEオブジェクト[!DNL root\CIMV2]の読み取りの権限が必要です(Data Workbenchサーバーのサービス開始モードを確認し、ローカルディスクの領域の割合を確認するために必要です)

1. 監視レコードが蓄積されるに従ってVSLファイルのサイズが拡大し始めていることを確認します。 小規模なインストールではトラフィック量が極めて少なくなるので(10分ごとに、ホスト固有のデータに対するヒットが1回だけ送信され、処理プロファイルあたり1回のヒットが送信されます)、この処理には時間がかかります。
1. insight_monitor.zip\profiles\Insight Historic to a temporary locationを解凍します。
1. [!DNL profile.cfg]、[!DNL dataset\cluster.cfg]、および[!DNL dataset\segment export.cfg]のホスト名を更新します。

1. Data Workbenchプロファイルディレクトリにファイルを更新します。
1. [!DNL dataset\log processing.cfg]内のログサーバーとパスを、Sensor VSLが蓄積する場所に更新します。
1. [] オプションで、プロファイル [!DNL Insight Profile Status] と [!DNL Insight Server Status]とも同じようにします。さらに、ステータスプロファイルは、最後の2日間のウィンドウで夜間に再処理する必要があります。 Windows追加予定タスク:プログラムは[!DNL e:\insight_monitor\insight_reprocess.exe]です。 引数は[!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]です。 [!DNL start in]は空白のままにします。 &lt;a0/追加>&quot;insight server status&quot;*に対する別の予定タスク。**insight_reprocess.* exe開始時間を更新するには、 *log processing.* cfgに対する読み取り/書き込みアクセス権が必要です。

1. さらに、ステータスプロファイルは、最後の2日間のウィンドウで夜間に再処理する必要があります。 Windows追加予定タスク:プログラムは&#x200B;*e:\insight_monitor\insight_reprocess.exe*&#x200B;です。 引数は — [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]です。 *開始は*&#x200B;空白のままにします。 &lt;a0/追加>の別のスケジュールされたタスク。 [!DNL "insight server status"][!DNL insight_reprocess.exe] 開始時間を更新するには、への読み取り/書き込みアクセス権 [!DNL log processing.cfg] が必要です。各プロファイルがモニターVSLを累積的に読み取っていることを確認します。 ここでも、非常に少ないボリュームのため、この処理には多少の時間（おそらく数時間）がかかります。

## インストールに関する注意{#section-17722441ab0046fcbcb46b957d56230a}

* **ライセンスを取得したテスト環境での監視プロファイルの設定**。テスト環境パッケージは、Data Workbenchの実装に含まれており、このパッケージを使用して、アプリケーションをインストールおよび設定できます。 実稼働FSUまたはDPUサーバーにインストールする場合は、サーバーを別のポートで実行するように設定する必要があります。
* **監視プロファイル専用の新しいセンサーの導入**。監視プロファイルーを実行しているサーバーに、Sensorの新しいインスタンスをインストールする必要があります。 これは、Sensorの実稼働インスタンスに加えて必要です。 (Sensorを実稼働サーバーまたは実稼働プロファイル以外のサーバーにインストールする場合、監視サーバー専用に追加料金は発生しません)。
* **Data Workbenchのメンテナンス中にモニターエージェントを無効にします**。稼働時間とパフォーマンス指標を汚染しないように、サービスInsightServer(Omniture Insightサーバー)のサービス開始モードを手動に設定できます。 便利なPowerShellコマンドは、*set-service -name insightserver -startuptype manual*&#x200B;です。 メンテナンス後に自動に戻す：*set-service -name insightserver -startuptype automatic*。 もう1つの方法は、モニターエージェントのスケジュールされたタスクを一時的に無効にすることです。
* **「Status」プロファイルは、古いホストとプロファイル、および古いホストとプロファイルのマッピングを削除するための最後の** ウィンドウが必要です。ただし、イベントデータの量が非常に小さく、data workbenchがバッファーしない場合は、処理を行うためにウィンドウのサイズをかなり拡張する必要がある場合があります。
* **エージェントは、Data Workbenchの詳細なステータス**(イベントデータログのタイムスタンプがUTC(VSLファイルなど)であると仮定してローカルホスト時間で報告)から、全体的で最も古い基準日時を収集します。イベントデータのタイムスタンプがUTC以外のタイムゾーンにある場合、結果のインサイトプロファイルステータスプロファイルで基準日時がオフセットされます。 イベントデータのタイムスタンプの&#x200B;**すべて**&#x200B;が同じタイムゾーンにある場合は、*InsightプロファイルーStatus\metrics\as of delay minutes.metric*&#x200B;にそのオフセットを追加できます。

* **2つの新しいディメンションが導入され、実稼動、ステージング、テストサーバー、他の状態のサーバーなど、異なる状態のサーバーを顧客グループに含めるのに役立ちます**。例えば、「uptime」を探している場合、実稼働モードでのみサーバーを調べます。 その結果、Groupディメンションは、必要に応じて任意にサーバーをグループ化する1つの方法にすぎません。 例えば、監視設定ファイルでは、オペレーション、開発、マーケティングなど、部門がサービスを提供するホストを設定できます。
