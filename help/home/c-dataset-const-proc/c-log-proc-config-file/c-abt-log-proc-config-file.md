---
description: Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。
title: ログ処理設定ファイルについて
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 76%

---

# ログ処理設定ファイルについて{#about-the-log-processing-configuration-file}

{{eol}}

Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。

データセットに関する以下のような設定を行う際は、[!DNL Log Processing.cfg] ファイルの編集が必要となります。

* ログソースを指定する。詳しくは、 [ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* ログ処理時にデータセットに追加するログエントリを絞り込む。詳しくは、 [データフィルター](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) および [ログエントリ条件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* 大量のイベントデータを伴った追跡 ID の分割を有効にする。詳しくは、[キー分割](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)を参照してください。
* ファイルサーバーユニットとして実行するように Data Workbench サーバーを設定する。詳しくは、 [Insight サーバーのファイルサーバーユニットの設定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* 中央の正規化サーバーとして実行するように Data Workbench サーバーを設定する。詳しくは、 [Insight サーバーのファイルサーバーユニットの設定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] ファイルには、データセット構築のログ処理段階に関する追加の手順を含めることができます。 継承されたプロファイルごとに、Dataset\Log Processing ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（Site アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。詳しくは、 [!DNL Log Processing Dataset Include] ファイル： [データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Site 用の Web 固有の設定パラメーターについて詳しくは、 [Web データの設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
