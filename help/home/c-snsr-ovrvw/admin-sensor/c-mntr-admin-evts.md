---
description: Sensorのエラーをできるだけ早く検出し、重大な問題や障害が発生する前に修復するには、イベントログを定期的に監視する必要があります。
solution: Analytics
title: 管理イベントの監視
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# 管理イベントの監視{#monitoring-administrative-events}

Sensorのエラーをできるだけ早く検出し、重大な問題や障害が発生する前に修復するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 少なくとも1時間

これらのイベントは、WindowsイベントビューアまたはUnix Syslogファイルを使用して監視できます。また、デフォルトでは、インストー [!DNL *.sensor-log] ルディレクトリ内の [!DNL Logs][!DNL Sensor] フォルダーにあるファイルも監視できます。 これらのファイルは、データ収集中にエラーが発生したことを示します。特に、がターゲットに接続できない場合、および開始がデータをキューに入れている [!DNL Sensor][!DNL data workbench server] 場合に、エラーが発生します。

## Windowsでのイベントの監視 {#section-7c0443a356af4381bf22259654f5cd17}

Sensorは、「Adobe」のソースを持つWindowsイベントViewerのアプリケーションログにエラーを記録します。

メッセージは、その重大度に応じて、「Information」、「Warning」または「Error」として記録されます。

**Windowsイベントビューアを開くには**:

* **開始/Campaign コントロールパネル/管理ツール/イベントビューアをクリックします**。

## Unixでのイベントの監視 {#section-5de3947891fb47ac88b7c855e545d54a}

センサーは、デー [!DNL syslog] モンにエラーを記録します。

syslogデーモンは、syslog.confファイルで指定した規則に基づいて、ログファイルにエラーメッセージを書き込みます。 エラーは、「LOG_DAEMON」というフラグと、重大度に応じて「LOG_NOTICE」または「LOG_ERR」というフラグで記録されます。

**Unixのsyslogを開くには**

Unixのsyslogは、通常、またはにあ [!DNL /var/adm/messages] り [!DNL /var/log/messages]ます。

適切な場所を参照し、syslogを開きます。

## メッセージ形式について {#section-a0899add30fd4b2da58a23b9e3324693}

すべてのSensorメッセージには文字列「Sensor」が含まれ、表示中のメッセージの重要性を反映するように番号が付けられます。

| メッセージ番号 | メッセージの意味 | メッセージ文字列 |
|---|---|---|
| 1xxx | 情報 | センサー情報# |
| 2xxx | 警告 | センサーの警告# |
| 3xxx | 設定エラー | センサーエラー# |
| 4xxx | 操作エラー | センサーエラー# |
| 5xxx | 内部エラー | センサーエラー# |

>[!NOTE]
>
>警告(2xx)は現在使用されていません。 これらの番号は、将来的に使用するために予約されています。

ネットワーク管理ツールは、「Sensor」ソースに関するエラーが発生した場合に5 ～ 10分ごとにメッセージを監視し、介入が必要な問題に関する適切な担当者に警告するように設定できます。 「Sensor Error」文字列など、特定の種類のイベントメッセージについてのみ、システムを監視するように選択できます。 また、「Sensor Info」、「Sensor Warning」および「Sensor Error」の文字列が前に付いたイベントに別のルールを適用することもできます。

## 重要なメッセージの識別 {#section-5a20f5dc18ca4012931d194db855e54e}

イベントログ内では、キューサイズに関するメッセージに特に注意し、直ちに対処する必要があります。

例えば、「 [!DNL Sensor Info 1012: Adobe disk queue is #% full]」などのメッセージは注意が必要です。

## センサーイベントメッセージへの応答 {#section-0004c4a169dc4a8882d9bd87dd326ad4}

サポートされるWebサーバープラットフォームに対するSensorのイベントと推奨されるアクションを示す表です。

**すべてのプラットフォーム**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> イベントメッセージ </th> 
   <th colname="col2" class="entry"> 推奨されるアクション </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> センサー情報1010:センサーが初期化されました。 </td> 
   <td colname="col2"> 操作は必要ありません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1011:センサーが終了しました。 キューに登録された合計クリック数## </td> 
   <td colname="col2"> 操作は必要ありません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1012:Adobeディスクキューが#%いっぱいです </td> 
   <td colname="col2"> このメッセージは、ディスクキューの使用率が10%のしきい値を超えるたびに記録されます。 この割合が引き続き増える場合は、キューがいっぱいになってデータが失われる前にアクションを実行する必要があります。 最も可能性の高い問題は、センサーがInsightサーバーとの通信を停止したことです。 AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1013:センサーの設定が変更されました </td> 
   <td colname="col2"> 操作は必要ありません。 Sensorは、設定ファイルの1つに変更が検出され、リロードします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1014:乱数ジェネレータのシード処理に問題があります </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1016:設定ファイル名が読み込まれました </td> 
   <td colname="col2"> 操作は必要ありません。 Sensorは、一覧表示された設定ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1017:テストファイル名が読み込まれました </td> 
   <td colname="col2"> 操作は必要ありません。 センサーは、一覧表示されたテストファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorエラー3016:設定ファイル/mypath/myfileを読み込めません </td> 
   <td colname="col2"> Webサーバー設定で指定されたSensor設定ファイルが存在し、Webサーバープロセスが読み取るために必要な権限があることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensor 3017:制御されたテスト構成ファイル/mypath/myfileを読み込めません </p> </td> 
   <td colname="col2"> <p>txlogd.confで指定した制御実験ファイルが存在し、txlogdプロセスにファイルを読み取るために必要な権限があることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorエラー3018:コンテンツフィルタリストを解析できません。 txlogd構成ファイルの確認 </td> 
   <td colname="col2"> txlogd.confのContentFilterIncludeエントリとContentFilterExcludeエントリの構文を確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3023:ロック(g_lockThrottle)の作成に失敗しました </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3024:ロックの作成に失敗しました(g_lockConfigCheck) </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorエラー4014:ディスクキューを開けませんでした。 </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4020:キューファイルではありません </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4021:キューがいっぱいです </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4022:長さ&lt;x&gt;のメモリブロックをオフセット&lt;y&gt;でマップできません </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorエラー5012:ミューテックスを作成できませんでした。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensorエラー5013:ミューテックスを取得できませんでした。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5030:フォークの生成エラー。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5031:setsidに失敗しました。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5032:フォークの生成エラー。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5033:chdirに失敗しました。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5034:受信したシグナル </td> 
   <td colname="col2"> プログラムは外部シグナルによって終了された可能性があります。 このシグナルのソースを特定できない場合は、AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5035:外部のメインから呼び出された出口 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5036:txlogdは既に実行中です </td> 
   <td colname="col2"> txlogdデーモンの別のインスタンスが既に実行中です。 新しいインスタンスを実行する場合は、最初に他のインスタンスを停止します。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTPサーバー**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| Sensorエラー3015:VisualSciencesConfigディレクティブがhttpd.confにありません。 | これは設定エラーです。 VisualSciencesConfigディレクティブは、httpd.conf内にtxlogd.confの場所を示すパラメーターを指定する必要があります。 |
| Sensorエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 | AdobeのClientCareにお問い合わせください。 |
| センサーエラー3025:サブリクエストがそれ自体を指す | AdobeのClientCareにお問い合わせください。 |

**AOLサーバ**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| Sensorエラー3015:ns/server/[server]/module/[module] sectionがAOLServer設定ファイルにありません。 | これは設定エラーです。 誤って記載されたとおりに訂正しなさい。 |
| Sensorエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 AdobeのClientCareにお問い合わせください。 | サポートにお問い合わせください。 AdobeのClientCareにお問い合わせください。 |
| センサーエラー3020:AOLServer設定ファイルの [セクション] セクションにVisualSciencesConfigが最初のエントリとして見つかりません。 | これは設定エラーです。 誤って記載されたとおりに訂正しなさい。 |
| センサーエラー3021:AOLServer構成ファイルの [section] セクションにVisualSciencesConfigの値がありません。 | これは設定エラーです。 誤って記載されたとおりに訂正しなさい。 |

**iPlanetおよびJavaシステムWebサーバ**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| Sensorエラー3011:初期ディレクティブが必要です。 例：Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | これは設定エラーです。 iPlanet initディレクティブがありません。 |
| Sensorエラー3015:config-fileがiPlanet Initディレクティブで指定されていません | これは設定エラーです。 構成ファイルへのパスがiPlanet Initディレクティブで指定されていません。 |
| Sensorエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 構成ファイルを確認してください | vys-cookieは、各ソフトウェア仮想サーバの最初のNameTransディレクティブとして指定する必要があります。 |

