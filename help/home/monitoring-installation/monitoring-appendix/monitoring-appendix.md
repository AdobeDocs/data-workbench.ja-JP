---
description: このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンション、指標を含むプロファイルについて説明します。
title: Data Workbench プロファイルのディメンションと指標
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench プロファイルのディメンションと指標{#data-workbench-profile-dimensions-and-metrics}

このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンション、指標を含むプロファイルについて説明します。

Data Workbenchサーバーを監視するには、特定のサーバー情報も取得しながら、詳細なステータスを解析するスクリプトを使用してデータを収集します。 次に、Data Workbenchサーバーの情報がページタグ呼び出しに渡され、Data Workbench Sensorが収集してVSLファイルに保存します。

## Data Workbench監視プロファイル{#section-b5b1234f55c3407dae8e68b031b7cd7f}が採用するプロファイル

これらのプロファイルは、サーバーの状態とパフォーマンスのデータを表示できるディメンションと指標を提供します。

* [InsightプロファイルステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [InsightサーバーステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Insight履歴プロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight履歴監視プロファイルの指標](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

ステータスプロファイルを使用すると、Data Workbenchの現在の動作を、運用上の観点から確認できます。 **Profile Status**&#x200B;プロファイルと&#x200B;**Server Status**&#x200B;プロファイルは、Detailed StatusとData Workbenchサーバーからデータを収集します。 収集されたすべてのデータは、使用するために`cs-uri-query`フィールドに配置されます。

**履歴プロファイル**&#x200B;を使用すると、履歴データを使用して構成とハードウェアの変更の影響を評価できます。 履歴プロファイルは、構成とハードウェアの変更が時間の経過と共に及ぼす影響を評価できるので、最も役に立つ場合があります。
