---
description: Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。
title: Data Workbench の Transform.cfg ファイルのサンプル
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 58%

---

# Data Workbench の Transform.cfg ファイルのサンプル{#sample-data-workbench-transform-cfg-files}

Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。

* [シンプルなInsight Transform.cfgファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [CSV での出力](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [サンプリングされたログファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Web サイトのセクション別にログファイルを分割する](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

いずれのサンプルも、Data Workbench の [!DNL Transform.cfg] ウィンドウにファイルが表示されます。

## Data Workbench の単純な Transform.cfg ファイル {#section-b7e83cafa3a947c597bd09d316930190}

次の[!DNL Transform.cfg]ウィンドウでは、[!DNL Logs]ディレクトリから[!DNL .vsl]ファイルを読み取り、x-timestringフィールドとx-trackingidフィールドをLogs\VTディレクトリに格納されたテキストファイルに書き出す手順を示します。 ファイルのローテーション期間や出力ファイル名の形式が指定されていないので、各ファイルには1日分のデータが格納され、デフォルトの形式[!DNL %yyyy%%mm%%dd%-%x-mask%.txt]の名前が付けられます。

![](assets/cfg_VisualTransform_SimpleExample.png)

## CSV での出力 {#section-03916934ad574efc8695abbae54a1816}

次の[!DNL Transform.cfg]ウィンドウでは、Logsディレクトリから[!DNL .vsl]ファイルを読み取り、Logs\VT\CSV directoryディレクトリに格納されたコンマ区切り([!DNL .csv])ファイルにフィールド0 ～ 13を書き出す手順を示しています。 ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。出力ファイルは、[!DNL %yyyy%%mm%%dd%-%x-mask%.csv]形式の[!DNL .csv]ファイルです。

![](assets/cfg_VisualTransform_CSVExample.png)

## サンプルログファイル {#section-113b3b0c0c7547ea9536bb2f465c0875}

変換機能の設定によって、完全なログファイルの最新の簡略版を作成できます。数時間かかるデータセット全体の再処理時間を、数分または数秒にまで短縮し、データセットの設定をすばやくテストすることができます。以下に示したのは、そのために必要な変換機能の設定例です。

次の[!DNL Transform.cfg]ウィンドウでは、[!DNL .vsl]ファイルをLogsディレクトリから読み取り、x-timestringフィールドとx-trackingidフィールドをLogs\VTディレクトリに格納されたテキストファイルに書き出す手順を示します。 Hash Threshold の指定によって、データセットから特定の追跡 ID を除外し、100 件に 1 件の割合でサンプリングされたデータセットを作成します。ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。出力ファイルの名前は、デフォルトの形式[!DNL %yyyy%%mm%%dd%-%x-mask%.txt]です。

![](assets/cfg_VisualTransform_SampledExample.png)

## Web サイトのセクション別にログファイルを分割する {#section-2cac205cd3934d31abb6c6ed8780196d}

次の[!DNL Transform.cfg]ウィンドウでは、[!DNL .vsl]ファイルをLogsディレクトリから読み取り、x-timestringフィールドとx-trackingidフィールドをLogs\VTディレクトリに格納されたテキストファイルに書き出す手順を示します。 この正規表現変換（[!DNL RETransform]）は、cs-uri-stem フィールドを入力として受け取り、サイトのセクションを定義する新しいフィールド（x-site）を作成します。出力されるテキストファイル（それぞれ 1 日分のデータを含む）の名前には x-site フィールドが追加されます。

![](assets/cfg_VisualTransform_SplittingExample.png)
