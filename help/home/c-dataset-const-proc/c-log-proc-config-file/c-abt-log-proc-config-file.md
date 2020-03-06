---
description: Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。
solution: Analytics
title: ログ処理設定ファイルについて
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ログ処理設定ファイルについて{#about-the-log-processing-configuration-file}

Log Processing.cfg ファイルは、データセット構築のログ処理段階を制御します。この段階で、無作為に並んだデータがデータソース（ログソース）から読み込まれ、フィルターと変換が適用されます。

データセットに関する以下のような設定を行う際は、[!DNL Log Processing.cfg] ファイルの編集が必要となります。

* ログソースを指定する。詳しくは、 [ログソース](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* ログ処理時にデータセットに追加するログエントリを絞り込む。詳しくは、 [Data Filters](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) and [Log Entry Condition](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。

* 大量のイベントデータを伴った追跡 ID の分割を有効にする。詳しくは、[キー分割](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)を参照してください。
* ファイルサーバーユニットとして実行するように Data Workbench サーバーを設定する。詳しくは、 Insightサー [バーのファイルサーバーユニットの設定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。
* 中央の正規化サーバーとして実行するように Data Workbench サーバーを設定する。詳しくは、 Insightサー [バーのファイルサーバーユニットの設定](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] ファイルには、データセット構築のログ処理段階に関する追加の命令を含めることができます。 継承されたプロファイルごとに、Dataset\Log Processing ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（Site アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。ファイルについて詳しくは、 [!DNL Log Processing Dataset Include] 「データセットインクルードフ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。 SiteのWeb固有の設定パラメーターについて詳しくは、「Webデータの [設定」を参照してください](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)。

