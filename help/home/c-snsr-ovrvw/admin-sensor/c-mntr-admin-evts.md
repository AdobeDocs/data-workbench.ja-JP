---
description: Sensorのエラーをできるだけ早く検出し、重大な問題や障害が発生する前に修復するには、イベントログを定期的に監視する必要があります。
solution: Insight
title: 管理イベントの監視
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理イベントの監視{#monitoring-administrative-events}

Sensorのエラーをできるだけ早く検出し、重大な問題や障害が発生する前に修復するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 少なくとも1時間

これらのイベントは、WindowsイベントビューアまたはUnixのSyslogファイルと、デフォルトでインストールディレクトリ内の [!DNL *.sensor-log] フォルダにあるファイルを使 [!DNL Logs] 用して監視するこ [!DNL Sensor] とができます。 これらのファイルは、データ収集中にエラーが発生したことを示します。特に、がターゲットに接続できず、 [!DNL Sensor] データのキューへの格納を開始 [!DNL data workbench server] した場合に発生します。

## Windowsでのイベントの監視 {#section-7c0443a356af4381bf22259654f5cd17}

Sensorは、「Adobe」のソースを使用して、Windowsイベントビューアのアプリケーションログにエラーを記録します。

メッセージの重要度に応じて、「情報」、「警告」または「エラー」として記録されます。

**Windowsイベントビューアを開くには**:

* スタート/ **コントロールパネル/管理ツール/イベントビューアをクリックします**。

## UNIXでのイベントの監視 {#section-5de3947891fb47ac88b7c855e545d54a}

センサーは、デーモンにエラーを記録 [!DNL syslog] します。

syslogデーモンは、syslog.confファイルで指定した規則に基づいて、ログファイルにエラーメッセージを書き込みます。 エラーは、「LOG_DAEMON」フラグと、重大度に応じて「LOG_NOTICE」または「LOG_ERR」フラグで記録されます。

**Unixのsyslogを開くには**

Unixのsyslogは通常、またはにあり [!DNL /var/adm/messages] ます [!DNL /var/log/messages]。

適切な場所を参照し、syslogを開きます。

## メッセージ形式について {#section-a0899add30fd4b2da58a23b9e3324693}

すべてのSensorメッセージには「Sensor」という文字列が含まれ、表示されるメッセージの重要性を反映するように番号が付けられます。

| メッセージ番号 | メッセージの意味 | メッセージ文字列 |
|---|---|---|
| 1xxx | 情報 | センサー情報# |
| 2xxx | 警告 | センサーの警告# |
| 3xxx | 設定エラー | センサーエラー# |
| 4xxx | 操作エラー | センサーエラー# |
| 5xxx | 内部エラー | センサーエラー# |

>[!NOTE]
>
>警告(2xxx)は現在使用されていません。 これらの数字は将来の使用のために予約されています。

ネットワーク管理ツールは、「Sensor」のソースに関するエラーが5 ～ 10分ごとにメッセージを監視し、介入が必要な可能性のある問題に関する適切な担当者に警告するように設定できます。 「Sensor Error」文字列など、特定のタイプのイベントメッセージについてのみ、システムを監視するように選択できます。 また、「Sensor Info」、「Sensor Warning」および「Sensor Error」の文字列が前に付いたイベントに異なるルールを適用することもできます。

## 重要なメッセージの識別 {#section-5a20f5dc18ca4012931d194db855e54e}

イベントログ内で、キューのサイズに関するメッセージに特に注意し、即座に対処する必要があります。

例えば、「」などのメッセージは [!DNL Sensor Info 1012: Adobe disk queue is #% full]注意が必要です。

## センサーイベントメッセージへの応答 {#section-0004c4a169dc4a8882d9bd87dd326ad4}

サポートされるWebサーバープラットフォームのセンサーイベントと推奨アクションを示す表。

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
   <td colname="col2"> 操作は不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1011:センサーが終了しました。 キューに登録された合計クリック数## </td> 
   <td colname="col2"> 操作は不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1012:アドビのディスクキューが#%いっぱいです </td> 
   <td colname="col2"> このメッセージは、ディスクキューの使用率が10%のしきい値を超えるたびに記録されます。 この割合が増え続ける場合は、キューがいっぱいになってデータが失われる前にアクションを実行する必要があります。 最も可能性の高い問題は、SensorがInsightサーバーとの通信を停止したことです。 Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1013:センサーの設定が変更されました </td> 
   <td colname="col2"> 操作は不要です。 Sensorは、設定ファイルの1つに変更を検出し、リロードします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1014:乱数ジェネレーターのシード処理の問題 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1016:読み込まれた設定ファイル名 </td> 
   <td colname="col2"> 操作は不要です。 センサーは、表示された設定ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1017:読み込まれたテストファイル名 </td> 
   <td colname="col2"> 操作は不要です。 センサーは、一覧表示されたテストファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3016:設定ファイル/mypath/myfileを読み込めません </td> 
   <td colname="col2"> Webサーバー設定で指定されたSensor設定ファイルが存在し、Webサーバープロセスで読み取る必要のある権限があることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー3017:制御実験の構成ファイル/mypath/myfileを読み込めません </p> </td> 
   <td colname="col2"> <p>txlogd.confで指定した制御実験ファイルが存在し、txlogdプロセスにファイルを読み取るために必要な権限があることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3018:コンテンツフィルタリストを解析できません。 txlogd設定ファイルの確認 </td> 
   <td colname="col2"> txlogd.conf内のContentFilterIncludeエントリとContentFilterExcludeエントリの構文を確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3023:ロックの作成に失敗しました(g_lockThrottle) </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3024:ロックの作成に失敗しました(g_lockConfigCheck) </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4014:ディスクキューを開けませんでした。 </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4020:キューファイルではありません </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4021:キューがいっぱいです </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4022:長さ&lt;x&gt;のメモリブロックをオフセット&lt;y&gt;にマップできません </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5012:mutexを作成できませんでした。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5013:ミューテックスを取得できませんでした。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5030:フォークの生成エラー。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5031:setsidに失敗しました。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5032:フォークの生成エラー。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5033:chdirに失敗しました。 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5034:信号受信 </td> 
   <td colname="col2"> プログラムは外部シグナルによって終了された可能性が高い。 このシグナルのソースが特定できない場合は、Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5035:外部のメインから呼び出された出口 </td> 
   <td colname="col2"> Adobe ClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5036:txlogdは既に実行中です </td> 
   <td colname="col2"> txlogdデーモンの別のインスタンスが既に実行されています。 新しいインスタンスを実行する場合は、最初に他のインスタンスを停止します。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| センサーエラー3015:VisualSciencesConfigディレクティブがhttpd.confにありません。 | これは設定エラーです。 VisualSciencesConfigディレクティブは、txlogd.confの場所を示すパラメーターと共にhttpd.conf内に存在する必要があります。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 | Adobe ClientCareにお問い合わせください。 |
| センサーエラー3025:サブリクエストがそれ自体を指す | Adobe ClientCareにお問い合わせください。 |

**AOLサーバー**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| センサーエラー3015:ns/server/[server]/module/[module] sectionがAOLServer設定ファイルにありません。 | これは設定エラーです。 誤って記載された通りに訂正しなさい。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 Adobe ClientCareにお問い合わせください。 | サポートにお問い合わせください。 Adobe ClientCareにお問い合わせください。 |
| センサーエラー3020:AOLServer設定ファイルのセクションセクションにVisualSciencesConfig [が] 1つ目のエントリとして見つかりません。 | これは設定エラーです。 誤って記載された通りに訂正しなさい。 |
| センサーエラー3021:AOLServer設定ファイルのセクションセクショ [ンに] 、VisualSciencesConfigの値がありません。 | これは設定エラーです。 誤って記載された通りに訂正しなさい。 |

**iPlanetおよびJavaシステムWebサーバ**

| イベントメッセージ | 推奨されるアクション |
|---|---|
| センサーエラー3011:初期ディレクティブが必要です。 例：Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | これは設定エラーです。 iPlanet initディレクティブがありません。 |
| センサーエラー3015:config-fileがiPlanet Initディレクティブで指定されていません | これは設定エラーです。 iPlanet Initディレクティブで、設定ファイルへのパスが指定されていません。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 設定ファイルを確認してください | vys-cookieは、各ソフトウェア仮想サーバの最初のNameTransディレクティブとして指定する必要があります。 |

