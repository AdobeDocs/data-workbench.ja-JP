---
description: Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。
title: Data Workbench の Transform.cfg ファイルのサンプル
uuid: cb473a5a-54e2-4bf7-84fb-c9c27910ef64
exl-id: f7aadde4-6d89-4bd4-b34b-192a81a71dc3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 58%

---

# Data Workbench の Transform.cfg ファイルのサンプル{#sample-data-workbench-transform-cfg-files}

{{eol}}

Transform.cfg ファイルでパラメーターを指定する方法について、いくつかのシナリオに沿って説明します。

* [単純な Insight Transform.cfg ファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-b7e83cafa3a947c597bd09d316930190)
* [CSV での出力](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-03916934ad574efc8695abbae54a1816)
* [サンプルログファイル](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-113b3b0c0c7547ea9536bb2f465c0875)
* [Web サイトのセクション別にログファイルを分割する](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/c-sample-transf-files.md#section-2cac205cd3934d31abb6c6ed8780196d)

いずれのサンプルも、Data Workbench の [!DNL Transform.cfg] ウィンドウにファイルが表示されます。

## Data Workbench の単純な Transform.cfg ファイル {#section-b7e83cafa3a947c597bd09d316930190}

以下 [!DNL Transform.cfg] ウィンドウに読み方を示す [!DNL .vsl] ファイル [!DNL Logs] ディレクトリに移動し、x-timestring フィールドと x-trackingid フィールドを Logs\VT ディレクトリに格納されたテキストファイルにエクスポートします。 ファイルのローテーション期間や出力ファイル名の形式が指定されていないので、各ファイルには 1 日分のデータが含まれ、デフォルトの形式の名前が付けられます [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SimpleExample.png)

## CSV での出力 {#section-03916934ad574efc8695abbae54a1816}

以下 [!DNL Transform.cfg] ウィンドウに読み方を示す [!DNL .vsl] ファイルを Logs ディレクトリから選択し、フィールド 0 ～ 13 をコンマ区切り ( [!DNL .csv]) ファイルを Logs\VT\CSV ディレクトリに保存します。 ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。出力ファイルは次のとおりです。 [!DNL .csv] 形式で指定されたファイル [!DNL %yyyy%%mm%%dd%-%x-mask%.csv].

![](assets/cfg_VisualTransform_CSVExample.png)

## サンプルログファイル {#section-113b3b0c0c7547ea9536bb2f465c0875}

変換機能の設定によって、完全なログファイルの最新の簡略版を作成できます。数時間かかるデータセット全体の再処理時間を、数分または数秒にまで短縮し、データセットの設定をすばやくテストすることができます。以下に示したのは、そのために必要な変換機能の設定例です。

以下 [!DNL Transform.cfg] ウィンドウに読み方を示す [!DNL .vsl] ファイルを Logs ディレクトリから取得し、x-timestring フィールドと x-trackingid フィールドを Logs\VT ディレクトリ内のテキストファイルにエクスポートします。 Hash Threshold の指定によって、データセットから特定の追跡 ID を除外し、100 件に 1 件の割合でサンプリングされたデータセットを作成します。ファイルのローテーション期間が指定されていないので、各ファイルには 1 日分のデータが格納されます。出力ファイルの名前はデフォルトの形式になっています [!DNL %yyyy%%mm%%dd%-%x-mask%.txt].

![](assets/cfg_VisualTransform_SampledExample.png)

## Web サイトのセクション別にログファイルを分割する {#section-2cac205cd3934d31abb6c6ed8780196d}

以下 [!DNL Transform.cfg] ウィンドウに読み方を示す [!DNL .vsl]ファイルを Logs ディレクトリから取得し、x-timestring フィールドと x-trackingid フィールドを Logs\VT ディレクトリ内のテキストファイルにエクスポートします。 この正規表現変換（[!DNL RETransform]）は、cs-uri-stem フィールドを入力として受け取り、サイトのセクションを定義する新しいフィールド（x-site）を作成します。出力されるテキストファイル（それぞれ 1 日分のデータを含む）の名前には x-site フィールドが追加されます。

![](assets/cfg_VisualTransform_SplittingExample.png)
