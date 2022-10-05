---
description: Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。
title: 変換設定ファイルについて
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 75%

---

# 変換設定ファイルについて{#about-the-transformation-configuration-file}

{{eol}}

Transformation.cfg ファイルは、データセット構築の変換段階を制御します。ログ処理段階で加工済みのデータに対し、この段階でさらにデータ変換が適用され、分析に使用できる拡張ディメンションが作成されます。

データセットに関する以下のような設定を行う際は、[!DNL Transformation.cfg] ファイルの編集が必要となります。

* ログ処理からデータをフィルタリングするには、 [!DNL log entry condition] 変換に使用します。
* 時間ディメンションの作成と時刻の変換に使用するタイムゾーンを設定する。詳しくは、 [タイムゾーン](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] ファイルには、データセット構築の変換段階に関する追加の手順を含めることができます。 継承されたプロファイルごとに、Dataset\Transformation ディレクトリにこれらのファイルが格納されます。アプリケーションごとのパラメーター（[!DNL Site] アプリケーションで必要となる Web サイト全体の設定パラメーターなど）は通常、このファイルで定義されます。詳しくは、 [!DNL Transformation Dataset Include] ファイル： [データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). Site 用の Web 固有の設定パラメーターについて詳しくは、 [Web データの設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
