---
description: このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンションおよび指標を含むプロファイルについて説明します。
solution: Analytics
title: Data Workbenchのプロファイルディメンションと指標
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchのプロファイルディメンションと指標{#data-workbench-profile-dimensions-and-metrics}

このドキュメントでは、Data Workbenchの監視プロファイルで使用されるフィールド、ディメンションおよび指標を含むプロファイルについて説明します。

Data Workbenchサーバーを監視するには、特定のサーバー情報も取り込みながら、詳細なステータスを解析するスクリプトを使用してデータを収集します。 次に、Data Workbenchサーバーの情報が、Data Workbench Sensorが収集してVSLファイルに保存するためのページタグ呼び出しに渡されます。

## Data Workbench監視プロファイルで使用されるプロファイル {#section-b5b1234f55c3407dae8e68b031b7cd7f}

次のプロファイルは、サーバーの状態とパフォーマンスデータを表示できるディメンションと指標を提供します。

* [Insightプロファイルステータスプロファイルのディメンション](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Insightサーバーステータスプロファイルのディメンション](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Insight Historicプロファイルのディメンション](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight Historical Monitoringプロファイルの指標](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

ステータスプロファイルを使用すると、Data Workbenchの現在のパフォーマンスを、運用上の観点から確認できます。 Profile Statusプロフ **ァイルと** Server Statusプロファイルは **** 、Detailed StatusサーバーとData Workbenchサーバーからデータを収集します。 収集されたすべてのデータがフィールドに配置さ `cs-uri-query` れ、使用されます。

履歴プ **ロファイル** (Historic Profiles)を使用すると、履歴データを使用して、構成とハードウェアの変更の影響を評価できます。 履歴プロファイルは、構成やハードウェアの変更が時間の経過と共に及ぼす影響を評価できるので、最も役に立つ場合があります。
