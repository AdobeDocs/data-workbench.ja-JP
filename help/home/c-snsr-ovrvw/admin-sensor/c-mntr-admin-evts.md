---
description: 重大な問題や機能停止を引き起こす前に、可能な限り早くセンサーエラーを検出し、修復するには、イベントログを定期的に監視する必要があります。
title: 管理イベント（センサ）の監視
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 1%

---

# 管理イベントの監視{#monitoring-administrative-events}

{{eol}}

重大な問題や機能停止を引き起こす前に、可能な限り早くセンサーエラーを検出し、修復するには、イベントログを定期的に監視する必要があります。

**推奨頻度：** 少なくとも 1 時間

これらのイベントは、Windows のイベントビューアまたは Unix の Syslog ファイルを使用して監視できます。 [!DNL *.sensor-log] デフォルトで [!DNL Logs] フォルダー内の [!DNL Sensor] インストールディレクトリ。 これらのファイルは、特に [!DNL Sensor] ターゲットに接続できません [!DNL data workbench server] およびがデータのキューを開始します。

## Windows でのイベントの監視 {#section-7c0443a356af4381bf22259654f5cd17}

センサーは、「Adobe」のソースで Windows イベントビューアのアプリケーションログにエラーを記録します。

メッセージは、重大度に応じて、「情報」、「警告」または「エラー」として記録されます。

**Windows イベントビューアを開くには**:

* クリック **スタート/Campaign コントロールパネル/管理ツール/イベントビューア**.

## UNIX でのイベントの監視 {#section-5de3947891fb47ac88b7c855e545d54a}

センサーは、 [!DNL syslog] デーモン。

syslog デーモンは、syslog.conf ファイルで指定したルールに基づいて、ログファイルにエラーメッセージを書き込みます。 エラーは、重大度に応じて、「LOG_DAEMON」フラグと「LOG_NOTICE」または「LOG_ERR」フラグでログに記録されます。

**Unix の syslog を開くには**

Unix の syslog は、通常、 [!DNL /var/adm/messages] または [!DNL /var/log/messages].

適切な場所を参照し、syslog を開きます。

## メッセージ形式について {#section-a0899add30fd4b2da58a23b9e3324693}

すべてのセンサーメッセージには「Sensor」という文字列が含まれ、表示されるメッセージの重要性を反映するように番号が付けられます。

| メッセージ番号 | メッセージの意味 | メッセージ文字列 |
|---|---|---|
| 1xxx | 情報 | センサー情報# |
| 2xxx | 警告 | センサーの警告番号 |
| 3xxx | 設定エラー | センサーエラー番号 |
| 4xxx | オペレーショナルエラー | センサーエラー番号 |
| 5xxx | 内部エラー | センサーエラー番号 |

>[!NOTE]
>
>警告 (2xxx) は現在使用されていません。 これらの数値は将来の使用のために予約されています。

ネットワーク管理ツールは、「センサー」のソースに関するエラーが発生した場合に 5～10 分ごとにメッセージを監視し、介入が必要な問題に関する適切な担当者に警告するように設定できます。 「Sensor Error」文字列など、特定のタイプのイベント・メッセージに対してのみシステムを監視するよう選択できます。 また、「Sensor Info」、「Sensor Warning」、「Sensor Error」の各文字列が前に付くイベントに、異なるルールを適用することもできます。

## 重要なメッセージの識別 {#section-5a20f5dc18ca4012931d194db855e54e}

イベントログ内で、キューのサイズに関するメッセージに特に注意し、即座に対処する必要があります。

例えば、「 [!DNL Sensor Info 1012: Adobe disk queue is #% full]「注意が必要です。

## センサーイベントメッセージへの対応 {#section-0004c4a169dc4a8882d9bd87dd326ad4}

次の表に、サポートされる Web サーバープラットフォームに対するセンサーイベントと推奨アクションを示します。

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
   <td colname="col1"> センサー情報 1010:センサーが初期化されました。 </td> 
   <td colname="col2"> アクションは不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1011:センサーが終了しました。 キューに入れられた合計クリック数## </td> 
   <td colname="col2"> アクションは不要です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1012:Adobeディスクキューが#%いっぱいです </td> 
   <td colname="col2"> このメッセージは、ディスクキューの使用率が 10%のしきい値を超えるたびに記録されます。 この割合が引き続き増加する場合は、キューがいっぱいになってデータが失われる前にアクションを実行する必要があります。 最も可能性の高い問題は、センサーが Insight サーバーとの通信を停止したことです。 AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1013:センサーの構成が変更されました </td> 
   <td colname="col2"> アクションは不要です。 センサーは、設定ファイルの 1 つに変更があることを検出し、リロードします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1014:乱数生成器のシードに問題があります </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1016:設定ファイル名が読み込まれました </td> 
   <td colname="col2"> アクションは不要です。 センサーが、リストされた設定ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサー情報 1017:実験ファイル名が読み込まれました </td> 
   <td colname="col2"> アクションは不要です。 センサーが、表示された実験ファイルを正常に読み込みました。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 3016:設定ファイル/mypath/myfile を読み込めません </td> 
   <td colname="col2"> Web サーバー設定で指定された Sensor 設定ファイルが存在し、Web サーバープロセスが読み取るために必要な権限があることを確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>センサー 3017:対照実験設定ファイル/mypath/myfile を読み込めません </p> </td> 
   <td colname="col2"> <p>txlogd.conf で指定された制御実験ファイルが存在し、txlogd プロセスがそのファイルを読み取るのに必要な権限を持っていることを確認します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 3018:コンテンツフィルターリストを解析できません。 txlogd 設定ファイルを確認 </td> 
   <td colname="col2"> txlogd.conf の ContentFilterInclude エントリと ContentFilterExclude エントリの構文を確認します。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 3023:ロックを作成できませんでした (g_lockThrottle) </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 3024:ロックを作成できませんでした (g_lockConfigCheck) </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 4014:ディスクキューを開けませんでした。 </td> 
   <td colname="col2"> txlogd.conf 内の QueueFile ファイル名を確認し、正しいと思われる場合は、AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 4020:キューファイルではありません </td> 
   <td colname="col2"> txlogd.conf 内の QueueFile ファイル名を確認し、正しいと思われる場合は、AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 4021:キューがいっぱいです </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 4022:長さのメモリブロックをマップできません &lt;x&gt; オフセット時 &lt;y&gt; </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5012:mutex を作成できませんでした。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5013:mutex を取得できませんでした。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5030:分岐の生成エラー。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5031:setsid が失敗しました。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5032:分岐の生成エラー。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5033:chdir に失敗しました。 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5034:受信したシグナル </td> 
   <td colname="col2"> プログラムが外部シグナルによって終了した可能性があります。 このシグナルのソースが判断できない場合は、AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5035:外部のメインから呼び出された出口 </td> 
   <td colname="col2"> AdobeClientCare にお問い合わせください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> センサーエラー 5036:txlogd は既に実行中です </td> 
   <td colname="col2"> txlogd デーモンの別のインスタンスが既に実行されています。 新しいインスタンスを実行する場合は、最初に別のインスタンスを停止します。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー 3015:VisualSciencesConfig ディレクティブが httpd.conf にありません。 | これは設定エラーです。 VisualSciencesConfig ディレクティブは、txlogd.conf の場所を示すパラメーターと共に httpd.conf 内に存在する必要があります。 |
| センサーエラー 3019:vys-cookie は、vys-log の前に呼び出されませんでした。 サポートにお問い合わせください。 | AdobeClientCare にお問い合わせください。 |
| センサーエラー 3025:サブリクエストはそれ自体を指す | AdobeClientCare にお問い合わせください。 |

**AOL サーバー**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー 3015:ns/server/[server]/module/[モジュール] のセクションが AOLServer 設定ファイルにありません。 | これは設定エラーです。 誤って記載された正しい。 |
| センサーエラー 3019:vys-cookie は、vys-log の前に呼び出されませんでした。 サポートにお問い合わせください。 AdobeClientCare にお問い合わせください。 | サポートにお問い合わせください。 AdobeClientCare にお問い合わせください。 |
| センサーエラー 3020:VisualSciencesConfig がの最初のエントリとして見つかりません [セクション] の節を参照してください。 | これは設定エラーです。 誤って記載された正しい。 |
| センサーエラー 3021:VisualSciencesConfig に値がありません： [セクション] の節を参照してください。 | これは設定エラーです。 誤って記載された正しい。 |

**iPlanet と Java System Web サーバー**

| イベントメッセージ | 推奨アクション |
|---|---|
| センサーエラー 3011:Init ディレクティブが必要です。 例えば、 Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | これは設定エラーです。 iPlanet init ディレクティブがありません。 |
| センサーエラー 3015:config-file が iPlanet Init ディレクティブで指定されていません | これは設定エラーです。 iPlanet Init ディレクティブで設定ファイルへのパスが指定されていませんでした。 |
| センサーエラー 3019:vys-cookie は、vys-log の前に呼び出されませんでした。 設定ファイルを確認してください | vys-cookie は、各ソフトウェア仮想サーバの最初の NameTrans ディレクティブとして指定する必要があります。 |
