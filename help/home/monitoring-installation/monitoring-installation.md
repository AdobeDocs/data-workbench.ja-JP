---
description: Data Workbench監視プロファイルのインストール方法を説明します。
solution: Analytics
title: 監視プロファイルのインストール
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 監視プロファイルのインストール{#installing-the-monitoring-profile}

Data Workbench監視プロファイルのインストール方法を説明します。

## インストール手順 {#section-d4355dbea8a447f48ab168db6ccff612}

1. タグ付きWebページのデータ収集に使用するかのように、新しいSensorインスタンスを設定します。 zig.gifファイルがSensor Webサーバーのドキュメントルートにあることを確認します。 センサーは、モニタープロファイルと同じホスト上で実行できます。 （この目的でテキストファイルを使用する場合は問題ありません）。

   >[!NOTE]
   >
   >このSensorインスタンスは、監視エージェントからのトラフィックのみを受信するように専用にする必要があります。 また、このコレクション用のWebサーバーを再利用する場合は、Sensorを別のポートで実行するように設定できます。

1. ファイル内 [!DNL txlogd.conf] のデフォルト行は次のとおりです。

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Data Workbench監視プロファイルアプリケーション（または「タグ付き」ページの実装）の場合、GIFファイルを使用して収集するには、画像タイプを削除する必要があります。 更新された行は次のとおりです。

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. を一時的な [!DNL insight_monitor.zip/insight_monitor_agent] 場所にコピーします。
1. 環境に合わ [!DNL insight_monitor_agent.cfg] せてファイルを更新します。 設定ファイル内のコメントに従います。

   **監視構成ファイル：**

   ![](assets/monitor_agent_cfg_sensor.png)

   すべての情報を収集する場所を定義し、URLアドレスを指定します。 これは、専用のセンサーである必要があり、このアプリケーション以外のトラフィックは受信しないでください。

   ![](assets/monitor_agent_cfg_dump.png)

   eがあると仮定したパスがあります。ディスク。 環境に合わせてこのパスを変更できます。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   Transformプロファイルを実行すると、Data Workbenchが応答しなくなる場合があります。 この値を使用すると、プロセスが応答しない状態で3回連続して送信された場合にアラートを送信できます。 これは、偽陽性のアラートを減らす方法です。

   ![](assets/monitor_agent_cfg_groups.png)

   ここで、環境ディメンションとグループディメンションを設定します。 これは、ホストによって異なる場合があります。

   ここでは、このパ ![](assets/monitor_agent_cfg_debug.png)スのエラー・ログを表示することで、モニタ・エージェントが何を実行しているかを正確に確認できます。

   ![](assets/monitor_agent_cfg_tempdb.png)

   これは、temp dbを内部的に使用するためです。 容量に達すると警告が表示される場合があります。 これは、物理ディスクの使用状況とは異なります。

1. Data Workbenchサーバーを実行する各DPUおよびFSUホストに ** 、insight_monitor_agentフォルダーをコピーします。 設定ファイルに示されているデフォルトの場所はですが、 [!DNL e:\insight_monitor_agent] この場所を変更することができます。

1. エージェントを10分ごとに呼び出すようにWindowsのスケジュールされたタスクを追加します（この期間は、処理レートの計算で想定されます）。 プログラムは [!DNL e:insight_monitor/insight_monitor_agent.exe]. 引数はconfig-file e:\insight_monitor\insight_monitor.cfgです。 e:\insight_monitorで開始します。 タスクを実行するユーザーは、Win32 OLEオブジェクトの読み取り/書き込みおよび読み取り権限が必要です [!DNL e:\insight_monitor][!DNL root\CIMV2] （Data Workbenchサーバーのサービスの開始モードを確認し、ローカルディスク上の領域の割合を確認するために必要）。

1. モニターレコードが蓄積されるにつれて、VSLファイルのサイズが拡大し始めていることを確認します。 小規模なインストールではトラフィック量が非常に少なくなるので、この処理には時間がかかります（エージェントは10分ごとに、ホスト固有のデータに対して1回のヒットと、処理プロファイルあたり1回のヒットのみを送信します）。
1. insight_monitor.zip\profiles\Insight Historic to a temporary locationを解凍します。
1. [!DNL]内のホ [!DNL profile.cfg]スト名と[!DNL [!DNL dataset\cluster.cfg]]、および[!DNL [!DNL dataset\segment export.cfg]]を更新します。

1. Data Workbenchプロファイルディレクトリにファイルを更新します。
1. ログサーバーと、センサーVSLが [!DNL dataset\log processing.cfg] 蓄積される場所のパスを更新します。
1. [オプション] で、およびに対しても同 [!DNL Insight Profile Status] じ操作を行いま [!DNL Insight Server Status]す。 さらに、ステータスプロファイルは、後続の2日間のウィンドウで毎晩再処理されます。 Windowsスケジュールタスクの追加：プログラムは [!DNL e:\insight_monitor\insight_reprocess.exe]. 議論は [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 空白のま [!DNL start in] まにします。 「Insightサーバーのステータス」に対し *て別のスケジュールされたタスクを追加しま*&#x200B;す。 *insight_reprocess.exeでは、開始時間を更新するために* 、log processing.cfg ** への読み取り/書き込みアクセス権が必要です。

1. さらに、ステータスプロファイルは、後続の2日間のウィンドウで毎晩再処理されます。 Windowsスケジュールタスクの追加：プログラムはe:\insight_monitor\insight_reprocess.exe *です*。 引数は — です [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 「 *start」は空白* 。 に対して別のスケジュール済みタスクを追加しま [!DNL "insight server status"]す。 [!DNL insight_reprocess.exe] 開始時間を更新するには、への読み取り/書 [!DNL log processing.cfg] き込みアクセス権が必要です。 各プロファイルがモニターVSLを読み取りながら蓄積していることを確認します。 この場合も、非常に少ないボリュームのため、おそらく数時間かかります。

## インストールに関する注意 {#section-17722441ab0046fcbcb46b957d56230a}

* **ライセンスを受けたテスト環境での監視プロファイルの設定**。 テスト環境パッケージは、Data Workbenchの実装に含まれており、アプリケーションのインストールと設定を行うことができます。 実稼働用FSUまたはDPUサーバーにインストールする場合は、別のポートで実行するようにサーバーを設定する必要があります。
* **監視プロファイル専用の新しいセンサーの導入**。 監視プロファイルを実行しているサーバーに、Sensorの新しいインスタンスをインストールする必要があります。 これは、Sensorの実稼働インスタンスに加えて、 （監視プロファイル用に、実稼動または非実稼働サーバーにSensorをインストールする場合、追加料金は発生しません）。
* **Data Workbenchのメンテナンス中にモニターエージェントを無効にします**。 稼働時間とパフォーマンス指標の汚染を防ぐために、サービスInsightServer (Omniture Insight Server)のサービス開始モードを手動に設定できます。 便利なPowerShellコマンドは、 *set-service -name insightserver -startuptype manualです*。 メンテナンス後に自動に戻す： *set-service -name insightserver -startuptype automatic*。 もう1つの方法は、モニターエージェントのスケジュールされたタスクを一時的に無効にすることです。
* **ステータス・プロファイルは、古いホスト** 、プロファイル、および古いホスト・プロファイルのマッピングを削除するための最後のウィンドウが必要です。 ただし、イベントデータの量が非常に少なく、Data Workbenchがバッファーしない場合は、処理するためにウィンドウのサイズをかなり拡張する必要がある場合があります。
* **エージェントは、Data Workbenchの詳細なステータス(イベントデータログのタイムスタンプがUTC（VSLファイルなど）であると仮定して**、ローカルホスト時間でレポートされる)から、全体的で最も古い日時を収集します。 イベントデータのタイムスタンプがUTC以外のタイムゾーンの場合、結果のインサイトプロファイルステータスプロファイルで基準時間がオフセットされます。 すべて **の** イベントデータのタイムスタンプが同じタイムゾーンにある場合は、そのオフセットを *Insight Profile Status\metrics\as of delay minutes.metricに追加できます*。

* **2つの新しいディメンションが導入され、異なる状態(実稼動、ステージング**、テストサーバー、他の状態のサーバーなど)のサーバーを顧客グループ化するのに役立ちます。 例えば、「uptime」を検索する場合は、実稼働モードでのみサーバーを参照します。 その結果、Groupディメンションは、必要に応じて任意にサーバーをグループ化する別の方法に過ぎません。 例えば、監視設定ファイルで、部門がサービスを提供するホスト（オペレーション、開発、マーケティングなど）を設定できます。

