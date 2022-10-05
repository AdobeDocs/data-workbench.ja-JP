---
description: Log Processing.cfg ファイル内の特定のパラメーターに関する補足情報へのリンクです。
title: ログ処理パラメーター
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 82%

---

# ログ処理パラメーター{#log-processing-parameters}

{{eol}}

Log Processing.cfg ファイル内の特定のパラメーターに関する補足情報へのリンクです。

<!--
c_data_filters.xml
-->

## データフィルター {#data-filters}

[!DNL Log Processing.cfg] ファイルには、次のようなフィルターが定義されています。

* End Time
* Hash Threshold
* Start Time

これらのパラメーターによって定義されたフィルタリングは、ログエントリがデコーダーから送出された後や変換された後、[!DNL Log Entry Condition] によって評価される前に適用されます。一般に、これらのパラメーターを 1 つでも変更すると、データセットの構成に変更が生じます。

[!DNL Sensor] のデータソースを使用して特定期間のデータセットを構築する場合、データセットの Start Time パラメーターと End Time パラメーターを使用することをお勧めします。

ログファイルを移動してディレクトリごとに分けるなどの方法よりも、Start Time パラメーターと End Time パラメーターを使用した方法を優先してください。データセットの開始時間と終了時間が設定されていれば、その指定された期間に生じたログエントリのみを Data Workbench サーバーが自動的に使用します。End Time が過去の時刻であれば、Data Workbench サーバーは通常、同じ一連のログエントリを使用してデータセットを更新します。新しい変換を追加するなどしてデータセットが更新されていたとしても同様です。

<!--
c_log_entry_con.xml
-->

## ログエントリ

基本的には、ログエントリの候補に対するフィルタリング処理と考えることができます。[!DNL Log Entry Condition] から false が返されたログエントリは候補から除外されます。

この [!DNL Log Entry Condition] は、条件演算 ( [条件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) と共に使用し、 [!DNL Sensor] ( *Data Workbench [!DNL Sensor] ガイド* )、または [!DNL Log Processing.cfg] ファイルを開き、テスト条件を定義します。 [!DNL Log Entry] の条件はログ処理時に適用されるほか、必要に応じて変換時に適用することもできます。

この例では、 [!DNL log entry condition] （web サイトデータ用） Web サイトの一部分に注目したデータセットや、そのサイトで特定のアクションを実行する訪問者に注目したデータセットを、[!DNL Log Entry Condition] を使用して作成できます。

この例の [!DNL Log Entry Condition] では、サイトの店舗に属するログエントリのみを含んだデータセットを作成しています。を使用する [!DNL RECondition test] 一致するパターンを持つ [!DNL "/store/.*"] そして [!DNL cs-uri-stem] フィールドは、文字列で始まる web ページのみを返します。 [!DNL "/store/"] は、データセットに含まれています。

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## キーの分割 {#key-split}

データセットに含まれる追跡 ID の数は人為的に増やされますが、Data Workbench サーバーによって処理されるログエントリの総数が増えることはありません。つまり、データセット内の可算イベント（指標）の合計数は維持されます。単一データが分割されると、以後、それらのデータには、2 つの異なる追跡 ID が永続的に割り当てられ、両者を関連付けることはできません。

例えば、Web データを扱う場合、追跡 ID は一意の訪問者を表します。キー分割を有効にした場合、データセット内の、大量のイベントデータを発生させた訪問者が複数の訪問者に分割されます。データセット内の訪問者数が人為的に増やされるのに対し、可算イベント（ページビュー、予約件数など）の総数が人為的に増やされることはありません。ただし分割後は、それぞれの訪問者のデータを相互に関連付けることはできません。

キー分割には、確率的アルゴリズムが使用されます。そのため、メモリ使用量、障害発生確率、キー分割しきい値（[!DNL Split Key Bytes]）、データセットサイズ間でトレードオフが生じます。以下の表に示す推奨設定は、障害の発生率を抑える設定となっています。イベントデータがキー分割しきい値を超えるエレメントのうち、約 22,000 個に 1 個（通常、1 データセットにつき 1 個未満）の割合で、分割されずに切り詰められるデータが生じます。

パラメーターごとの推奨値（キー分割あり／なし）を次の表に示します。

| パラメーター | キー分割なし | キー分割あり |
|---|---|---|
| Group Maximum Key Bytes | 1e6 | 2e6 |
| Split Key Bucket Space | 6e6 | 6e6 |
| Split Key Bytes | 0 | 1e6 |
| Split Key Space Ratio | 10 | 10 |

[!DNL Group Maximum Key Bytes] は、1 つの追跡 ID に対して処理できるイベントデータの最大量を指定します。 この制限を超えるデータは、データセット構築プロセスから除外されます。[!DNL Split Key Bytes] は、1 つの追跡 ID を複数のエレメントに分割するときの単位となるバイト数を表します。エレメントは、確率分布に従い、おおよそこのバイト数で分割されます。[!DNL Split Key Space Ratio] および [!DNL Split Key Bucket Space] キー分割のメモリ使用率と障害率を制御します。

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]、および [!DNL Split Key Bucket Space] キー分割が正しく機能するには、すべてを宣言する必要があります。 これらのパラメーターの値は変更しないでください（変更が必要な場合は必ずアドビまでご相談ください）。
