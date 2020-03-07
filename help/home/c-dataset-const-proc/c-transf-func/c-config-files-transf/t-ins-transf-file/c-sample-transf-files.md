---
description: Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。
solution: Analytics
title: Data Workbench の Transform.cfg ファイルのサンプル
topic: Data workbench
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench の Transform.cfg ファイルのサンプル{#sample-data-workbench-transform-cfg-files}

Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。

* [シンプルなInsight Transform.cfgファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [CSV での出力](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [サンプルログファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Web サイトのセクション別にログファイルを分割する](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

いずれのサンプルも、Data Workbench の [!DNL Transform.cfg] ウィンドウにファイルが表示されます。

## Data Workbench の単純な Transform.cfg ファイル {#section-b7e83cafa3a947c597bd09d316930190}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the [!DNL Logs] directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. Because no file rotation period or output file name format is specified, each file contains data for one calendar day and has a name in the default format [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## CSV での出力 {#section-03916934ad574efc8695abbae54a1816}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the Logs directory and export fields 0 through 13 to a comma-delimited ( [!DNL .csv]) file stored in the Logs\VT\CSV directory. ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。出力ファイルは、 [!DNL .csv] 形式で指定されたファイルで [!DNL %yyyy%%mm%%dd%-%x-mask%.csv]す。

![](assets/cfg_VisualTransform_CSVExample.png)

## サンプルログファイル {#section-113b3b0c0c7547ea9536bb2f465c0875}

変換機能の設定によって、完全なログファイルの最新の簡略版を作成できます。数時間かかるデータセット全体の再処理時間を、数分または数秒にまで短縮し、データセットの設定をすばやくテストすることができます。以下に示したのは、そのために必要な変換機能の設定例です。

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl] files from the Logs directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. Hash Threshold の指定によって、データセットから特定の追跡 ID を除外し、100 件に 1 件の割合でサンプリングされたデータセットを作成します。ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。The names of the output files are in the default format [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Web サイトのセクション別にログファイルを分割する {#section-2cac205cd3934d31abb6c6ed8780196d}

The following [!DNL Transform.cfg] window provides instructions to read [!DNL .vsl]files from the Logs directory and export the x-timestring and x-trackingid fields to a text file stored in the Logs\VT directory. この正規表現変換（[!DNL RETransform]）は、cs-uri-stem フィールドを入力として受け取り、サイトのセクションを定義する新しいフィールド（x-site）を作成します。出力されるテキストファイル（それぞれ 1 日分のデータを含む）の名前には x-site フィールドが追加されます。

![](assets/cfg_VisualTransform_SplittingExample.png)

