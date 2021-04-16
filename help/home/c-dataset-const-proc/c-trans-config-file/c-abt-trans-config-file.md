---
description: Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。
title: 変換設定ファイルについて
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 75%

---

# 変換設定ファイルについて{#about-the-transformation-configuration-file}

Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。

データセットに関する以下のような設定を行う際は、[!DNL Transformation.cfg] ファイルの編集が必要となります。

* 変換の[!DNL log entry condition]を定義することで、ログ処理からデータをフィルタリングする。
* 時間ディメンションの作成と時刻の変換に使用するタイムゾーンを設定する。詳しくは、 [タイムゾーン](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] ファイルには、データセット構築の変換段階で必要となる追加の命令を含めることができます。継承されたプロファイルごとに、Dataset\Transformation ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（[!DNL Site] アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。[!DNL Transformation Dataset Include]ファイルについて詳しくは、[データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)を参照してください。 SiteのWeb固有の設定パラメーターについて詳しくは、[Webデータの設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)を参照してください。
