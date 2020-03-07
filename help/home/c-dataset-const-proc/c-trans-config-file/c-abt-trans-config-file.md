---
description: Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。
solution: Analytics
title: 変換設定ファイルについて
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換設定ファイルについて{#about-the-transformation-configuration-file}

Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。

データセットに関する以下のような設定を行う際は、[!DNL Transformation.cfg] ファイルの編集が必要となります。

* Filtering data from log processing by defining the [!DNL log entry condition] for transformation.
* 時間ディメンションの作成と時刻の変換に使用するタイムゾーンを設定する。詳しくは、 [タイムゾーン](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] ファイルには、データセット構築の変換段階に関する追加の手順を含めることができます。 継承されたプロファイルごとに、Dataset\Transformation ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（[!DNL Site] アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。ファイルについて詳しくは、 [!DNL Transformation Dataset Include] 「データセットインクルードフ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)い。 SiteのWeb固有の設定パラメーターについて詳しくは、「Webデータの [設定」を参照してください](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

