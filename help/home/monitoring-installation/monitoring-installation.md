---
description: Data Workbench の監視プロファイルのインストール手順です。
title: 監視プロファイルのインストール
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# 監視プロファイルのインストール{#installing-the-monitoring-profile}

{{eol}}

Data Workbench の監視プロファイルのインストール手順です。

## インストール手順 {#section-d4355dbea8a447f48ab168db6ccff612}

1. 新しい Sensor インスタンスを、タグ付き Web ページのデータ収集に使用する場合と同じように設定します。 zig.gif ファイルが Sensor Web サーバーのドキュメントルートにあることを確認します。 センサーは、モニタープロファイルと同じホスト上で実行できます。 （この目的でテキストファイルを使用する場合は問題になりません）。

   >[!NOTE]
   >
   >この Sensor インスタンスは、監視エージェントからのトラフィックのみを受信するように専用にする必要があります。 また、このコレクション用に Web サーバーを再利用する場合は、別のポートで実行するようにセンサーを設定することもできます。

1. 内 [!DNL txlogd.conf] ファイルにはデフォルトの行があります。

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   Data Workbench Monitoring Profile アプリケーション（または「タグ付き」ページ実装）の場合、GIFファイルを介して収集するには、イメージタイプを削除する必要があります。 更新された行は次のとおりです。

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. を [!DNL insight_monitor.zip/insight_monitor_agent] を一時的な場所に追加します。
1. 更新 [!DNL insight_monitor_agent.cfg] ファイルを作成します。 設定ファイル内のコメントに従います。

   **監視設定ファイル：**

   ![](assets/monitor_agent_cfg_sensor.png)

   すべての情報を収集する場所を定義し、URL アドレスを指定します。 これは専用のセンサーである必要があり、このアプリケーション以外はトラフィックを受信しないでください。

   ![](assets/monitor_agent_cfg_dump.png)

   e があると仮定したパスがあります。ディスク。 このパスは、環境に合わせて変更できます。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   変換プロファイルを実行する際に、Data Workbench が応答しない場合があります。 この値を使用すると、プロセスが連続して 3 回応答しない場合にアラートを送信できます。 これは、偽陽性アラートを減らす方法です。

   ![](assets/monitor_agent_cfg_groups.png)

   ここで、環境ディメンションとグループディメンションを設定します。 ホストごとに異なる場合があります。

   これは w です ![](assets/monitor_agent_cfg_debug.png)ここでは、このパスのエラーログを表示することで、モニターエージェントが何を実行しているかを正確に確認できます。

   ![](assets/monitor_agent_cfg_tempdb.png)

   これは、temp db を内部で使用するためです。 処理能力に達する際に警告を受ける場合があります。 これは、物理ディスクの使用量とは異なります。

1. を *insight_monitor_agent* フォルダーを、Data Workbench サーバーを実行する各 DPU および FSU ホストに保存します。 設定ファイルに示されるデフォルトの場所は次のとおりです。 [!DNL e:\insight_monitor_agent] ただし、この場所は変更できます。

1. 10 分ごとにエージェントを呼び出す Windows スケジュールタスクを追加します（この期間は、処理レートの計算で想定されます）。 プログラムは [!DNL e:insight_monitor/insight_monitor_agent.exe]. 引数は config-file e:\insight_monitor\insight_monitor.cfgです。 e:\insight_monitorから始めます。 タスクを実行するユーザーは、読み取り/書き込み権限が必要です [!DNL e:\insight_monitor] Win32 OLE オブジェクトを読み取ります。 [!DNL root\CIMV2] （data workbench サーバーのサービスの開始モードを確認し、ローカルディスク上の領域の割合を確認するために必要）

1. 監視レコードが蓄積されるにつれて、VSLファイルが拡大し始めていることを確認します。 小規模なインストールではトラフィック量が非常に少なくなるので、この処理には時間がかかります（10 分ごとに、エージェントはホスト固有のデータのヒットを 1 回だけ送信し、処理プロファイルごとに 1 回ヒットします）。
1. insight_monitor.zip\profiles\Insight 一時的な場所に履歴を解凍します。
1. でホスト名を更新 [!DNL profile.cfg], [!DNL dataset\cluster.cfg]、および [!DNL dataset\segment export.cfg].

1. Data Workbench の profiles ディレクトリにファイルを更新します。
1. ログサーバーとパスを [!DNL dataset\log processing.cfg] を、Sensor VSLが蓄積している場所に追加します。
1. [オプション] プロファイルに対しても同じ処理を行う [!DNL Insight Profile Status] および [!DNL Insight Server Status]. さらに、ステータスプロファイルは毎晩、最後の 2 日間のウィンドウで再処理されます。 Windows スケジュールタスクの追加：プログラムは [!DNL e:\insight_monitor\insight_reprocess.exe]. この引数は [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 終了 [!DNL start in] 空白。 別の予定タスクの追加 *&quot;insight server status&quot;*. *insight_reprocess.exe* には読み取り/書き込みアクセス権が必要です *log processing.cfg* をクリックして開始時間を更新します。

1. さらに、ステータスプロファイルは毎晩、最後の 2 日間のウィンドウで再処理されます。 Windows スケジュールタスクの追加：プログラムは *e:\insight_monitor\insight_reprocess.exe*. 引数は — です。 [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 終了 *開始* 空白。 別の予定タスクの追加 [!DNL "insight server status"]. [!DNL insight_reprocess.exe] には読み取り/書き込みアクセス権が必要です [!DNL log processing.cfg] をクリックして開始時間を更新します。 各プロファイルが累積したモニターVSLを読み取っていることを確認します。 この場合も極めて少量なので、時間がかかる（おそらく数時間）。

## インストールに関する注意 {#section-17722441ab0046fcbcb46b957d56230a}

* **ライセンスを持つテスト環境での監視プロファイルの設定**. Data Workbench の実装には、テスト環境パッケージが含まれており、アプリケーションをインストールして設定できます。 実稼動 FSU または DPU サーバーにインストールする場合は、別のポートで実行するようにサーバーを設定する必要があります。
* **監視プロファイル専用の新しいセンサーのデプロイ**. 監視プロファイルを実行するサーバーに、新しい Sensor インスタンスをインストールする必要があります。 これは、Sensor の実稼動インスタンスに加えておこなわれます。 （モニタリングプロファイル用の実稼働サーバーまたは非実稼働サーバーにセンサーをインストールする場合、追加料金は発生しません）。
* **Data Workbench のメンテナンス中にモニターエージェントを無効にする**. 稼動時間とパフォーマンスの指標を汚染しないように、サービスの開始モードを手動に設定して、InsightServer(Omniture Insight Server) に対応させることができます。 便利な PowerShell コマンドは次のとおりです。 *set-service -name insightserver -startuptype manual*. メンテナンス後に自動に戻す： *set-service -name insightserver -startuptype automatic*. もう 1 つのオプションは、モニターエージェントのスケジュール済みタスクを一時的に無効にすることです。
* **ステータスプロファイルには末尾のウィンドウが必要です** 古いホストおよびプロファイルおよび古いホストプロファイルマッピングを削除する。 ただし、イベントデータの量が非常に小さく、Data Workbench がバッファーしない場合は、処理を行うために、ウィンドウのサイズをかなり拡張する必要が生じる場合があります。
* **エージェントは、Data Workbench の詳細なステータスから、全体的で最も古い現在の状態を収集します**：イベントデータログのタイムスタンプが UTC(VSLファイルなど ) であると仮定して、ローカルホスト時間でレポートされます。 イベントデータのタイムスタンプが UTC 以外のタイムゾーンにある場合、現在時刻は結果の Insight プロファイルステータスプロファイルでオフセットされます。 If **すべて** イベントデータのタイムスタンプが同じタイムゾーンにある場合、そのオフセットを *インサイトプロファイルステータス\metrics\遅延時間（分）.metric*.

* **異なる状態にある場合に顧客グループ化を支援する、2 つの新しいディメンションが導入されました。**（実稼動、ステージング、テストサーバー、他の状態のサーバーなど）。 例えば、「uptime」を探している場合は、本番モードでのみサーバを確認します。 その結果、グループディメンションは、必要に応じて任意にサーバーをグループ化するもう 1 つの方法です。 たとえば、監視構成ファイルで、オペレーション、開発、マーケティングなど、部門がサービスを提供するホストを設定できます。
