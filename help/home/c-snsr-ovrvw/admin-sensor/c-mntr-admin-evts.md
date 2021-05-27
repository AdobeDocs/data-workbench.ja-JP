---
description: センサーエラーを可能な限り早く検出し、重大な問題や停止を引き起こす前に修復するには、イベントログを定期的に監視する必要があります。
title: 管理イベントの監視
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# 管理イベントの監視{#monitoring-administrative-events}

センサーエラーを可能な限り早く検出し、重大な問題や停止を引き起こす前に修復するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 少なくとも1時間

これらのイベントは、WindowsイベントビューアまたはUnixのSyslogファイルと、デフォルトで[!DNL Sensor]インストールディレクトリ内の[!DNL Logs]フォルダーにある[!DNL *.sensor-log]ファイルを使用して監視できます。 これらのファイルは、データ収集中にエラーが発生したことを示します。特に、[!DNL Sensor]がターゲット[!DNL data workbench server]に接続できず、データのキューへの格納を開始する場合です。

## Windowsでのイベントの監視{#section-7c0443a356af4381bf22259654f5cd17}

センサーは、「Adobe」のソースを持つWindowsイベントビューアのアプリケーションログにエラーを記録します。

メッセージは、重大度に応じて、「情報」、「警告」または「エラー」として記録されます。

**Windowsイベントビューアを開くには**:

* **開始/Campaign コントロールパネル/管理ツール/イベントビューア**&#x200B;をクリックします。

## Unixでのイベントの監視{#section-5de3947891fb47ac88b7c855e545d54a}

センサーは、[!DNL syslog]デーモンにエラーを記録します。

syslogデーモンは、syslog.confファイルで指定した規則に基づいて、ログファイルにエラーメッセージを書き込みます。 エラーは、重大度に応じて、「LOG_DAEMON」フラグと「LOG_NOTICE」または「LOG_ERR」フラグでログに記録されます。

**Unix syslogを開くには**

Unixのsyslogは、通常、[!DNL /var/adm/messages]または[!DNL /var/log/messages]にあります。

適切な場所を参照し、syslogを開きます。

## メッセージ形式{#section-a0899add30fd4b2da58a23b9e3324693}について

すべてのセンサーメッセージには、「Sensor」という文字列が含まれ、表示されるメッセージの重要性を反映するように番号が付けられます。

| メッセージ番号 | メッセージの意味 | メッセージ文字列 |
|---|---|---|
| 1xxx | 情報 | センサー情報# |
| 2xxx | 警告 | センサー警告# |
| 3xxx | 構成エラー | センサーエラー# |
| 4xxx | 操作エラー | センサーエラー# |
| 5xxx | 内部エラー | センサーエラー# |

>[!NOTE]
>
>警告(2xxx)は現在使用されていません。 これらの数値は、今後の使用のために予約されています。

ネットワーク管理ツールは、「センサー」のソースに関するエラーが発生した場合に5～10分ごとにメッセージを監視し、介入が必要な可能性のある問題に関する適切な担当者に警告を出すように設定できます。 「Sensor Error」文字列など、特定のタイプのイベント・メッセージのみをシステムで監視するように選択できます。 また、「Sensor Info」、「Sensor Warning」、「Sensor Error」の各文字列が前に付いたイベントに別のルールを適用することもできます。

## 重要なメッセージの識別{#section-5a20f5dc18ca4012931d194db855e54e}

イベントログ内では、キューサイズに関するメッセージに特に注意し、即座に対処する必要があります。

例えば、「 [!DNL Sensor Info 1012: Adobe disk queue is #% full] 」などのメッセージは注意が必要です。

## センサーイベントメッセージへの応答{#section-0004c4a169dc4a8882d9bd87dd326ad4}

サポートされるWebサーバープラットフォームに対するセンサーイベントと推奨アクションを示す表。

**すべてのプラットフォーム**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> イベントメッセージ </th> 
   <th colname="col2" class="entry"> 推奨アクション </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> センサー情報1010:センサーが初期化されました。 </td> 
   <td colname="col2"> 操作は不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1011:センサーが終了しました。 キューに入れられた合計クリック数## </td> 
   <td colname="col2"> 操作は不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1012:Adobeディスクキューが#%いっぱいです </td> 
   <td colname="col2"> このメッセージは、ディスクキューの使用率が10%のしきい値を超えるたびに記録されます。 この割合が増え続ける場合は、キューがいっぱいになってデータが失われる前にアクションを実行する必要があります。 最も可能性の高い問題は、センサーがInsightサーバーとの通信を停止したことです。 AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1013:センサーの構成が変更されました </td> 
   <td colname="col2"> 操作は不要です。 センサーは、設定ファイルの1つに変更があることを検出し、再読み込みします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1014:乱数生成器のシードに問題があります </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1016:設定ファイル名が読み込まれました </td> 
   <td colname="col2"> 操作は不要です。 センサーは、表示された設定ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報1017:実験ファイル名が読み込まれました </td> 
   <td colname="col2"> 操作は不要です。 センサーが、表示された実験ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3016:設定ファイル/mypath/myfileを読み込めません </td> 
   <td colname="col2"> Webサーバー設定で指定されたセンサー設定ファイルが存在し、Webサーバープロセスが読み取る必要のある権限があることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー3017:制御実験構成ファイル/mypath/myfileを読み込めません </p> </td> 
   <td colname="col2"> <p>txlogd.confで指定した対照実験ファイルが存在し、ファイルを読み取るために必要な権限がtxlogdプロセスにあることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3018:コンテンツフィルタリストを解析できません。 txlogd設定ファイルの確認 </td> 
   <td colname="col2"> txlogd.confのContentFilterIncludeエントリとContentFilterExcludeエントリの構文を確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3023:ロック(g_lockThrottle)を作成できませんでした </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー3024:ロック(g_lockConfigCheck)を作成できませんでした </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4014:ディスクキューを開けませんでした。 </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、AdobeClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー4020:キューファイルではありません </td> 
   <td colname="col2"> txlogd.conf内のQueueFileファイル名を確認し、正しいと思われる場合は、AdobeClientCareにお問い合わせください。 </td> 
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
   <td colname="col1"> センサーエラー5012:mutexを作成できませんでした。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5013:mutexを取得できませんでした。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5030:スポーンフォークエラー。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5031:setsidに失敗しました。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5032:スポーンフォークエラー。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5033:chdirに失敗しました。 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5034:受信したシグナル </td> 
   <td colname="col2"> プログラムは外部シグナルによって終了した可能性があります。 このシグナルのソースが判断できない場合は、AdobeClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5035:外部のメインから呼び出された出口 </td> 
   <td colname="col2"> AdobeのClientCareにお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー5036:txlogdは既に実行中です </td> 
   <td colname="col2"> txlogdデーモンの別のインスタンスが既に実行されています。 新しいインスタンスを実行する場合は、最初に他のインスタンスを停止します。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTPサーバー**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー3015:VisualSciencesConfigディレクティブがhttpd.confにありません。 | これは設定エラーです。 VisualSciencesConfigディレクティブは、 txlogd.confの場所であるパラメーターを使用してhttpd.confに含める必要があります。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 | AdobeのClientCareにお問い合わせください。 |
| センサーエラー3025:サブリクエストは自分自身を指す | AdobeのClientCareにお問い合わせください。 |

**AOLサーバー**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー3015:ns/server/[server]/module/[module]セクションがAOLServer設定ファイルに見つかりません。 | これは設定エラーです。 誤りの記載通りに正しい。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 サポートにお問い合わせください。 AdobeのClientCareにお問い合わせください。 | サポートにお問い合わせください。 AdobeのClientCareにお問い合わせください。 |
| センサーエラー3020:AOLServer設定ファイルの[セクション]セクションにVisualSciencesConfigが最初のエントリとして見つかりません。 | これは設定エラーです。 誤りの記載通りに正しい。 |
| センサーエラー3021:VisualSciencesConfigにAOLServer設定ファイルの[セクション]セクションに値がありません。 | これは設定エラーです。 誤りの記載通りに正しい。 |

**iPlanetとJavaシステムWebサーバー**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー3011:Initディレクティブが必要です。 例えば、 Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | これは設定エラーです。 iPlanet initディレクティブが見つかりません。 |
| センサーエラー3015:config-fileがiPlanet Initディレクティブで指定されていません | これは設定エラーです。 iPlanet Initディレクティブで構成ファイルへのパスが指定されていません。 |
| センサーエラー3019:vys-cookieは、vys-logの前に呼び出されませんでした。 構成ファイルを確認してください | vys-cookieは、各ソフトウェア仮想サーバの最初のNameTransディレクティブとして指定する必要があります。 |
