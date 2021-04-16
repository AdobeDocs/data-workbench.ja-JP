---
description: このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンションおよび指標のプロファイルについて説明します。
title: Data Workbench プロファイルのディメンションと指標
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench プロファイルのディメンションと指標{#data-workbench-profile-dimensions-and-metrics}

このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンションおよび指標のプロファイルについて説明します。

Data Workbenchサーバーを監視するには、詳細なステータスを解析し、特定のサーバー情報も取得するスクリプトを使用してデータを収集します。 次に、Data Workbenchサーバーの情報がData Workbench Sensorのページタグ呼び出しに渡され、収集してVSLファイルに保存されます。

## Data Workbench監視プロファイルが使用するプロファイル{#section-b5b1234f55c3407dae8e68b031b7cd7f}

次のプロファイルには、サーバーの状態とパフォーマンスのデータを表示できるディメンションと指標が用意されています。

* [InsightプロファイルステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [InsightサーバーのステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [インサイト歴史プロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight Historical Monitoringプロファイルの指標](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

「ステータス」プロファイルを使用すると、data workbenchが現在どのように動作しているかを、操作上の観点から確認できます。 **プロファイルステータス**&#x200B;プロファイルと&#x200B;**サーバーステータス**&#x200B;プロファイルは、詳細ステータスとdata workbenchサーバーからデータを収集します。 収集されたすべてのデータは、使用する`cs-uri-query`フィールドに配置されます。

**履歴プロファイル**&#x200B;を使用すると、構成とハードウェアの変更が与える影響を履歴データを使用して評価できます。 過去のプロファイルは、構成とハードウェアの変更が時間の経過とともに及ぼす影響を評価できるので、最も役に立つ場合があります。
