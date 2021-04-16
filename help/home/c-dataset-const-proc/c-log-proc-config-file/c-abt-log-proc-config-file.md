---
description: Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。
title: ログ処理設定ファイルについて
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 76%

---

# ログ処理設定ファイルについて{#about-the-log-processing-configuration-file}

Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。

データセットに関する以下のような設定を行う際は、[!DNL Log Processing.cfg] ファイルの編集が必要となります。

* ログソースを指定する。詳しくは、 [ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* ログ処理時にデータセットに追加するログエントリを絞り込む。詳しくは、  [Data ](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) Filtersと [Log Entry Condition](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。

* 大量のイベントデータを伴った追跡 ID の分割を有効にする。詳しくは、[キー分割](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)を参照してください。
* ファイルサーバーユニットとして実行するように Data Workbench サーバーを設定する。詳しくは、  [Insightサーバーのファイルサーバーユニットの設定を参照してください](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。
* 中央の正規化サーバーとして実行するように Data Workbench サーバーを設定する。詳しくは、  [Insightサーバーのファイルサーバーユニットの設定を参照してください](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] ファイルには、データセット構築のログ処理段階で必要となる追加の命令を含めることができます。継承されたプロファイルごとに、Dataset\Log Processing ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（Site アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。[!DNL Log Processing Dataset Include]ファイルについて詳しくは、[データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。 SiteのWeb固有の設定パラメーターについて詳しくは、[Webデータの設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)を参照してください。
