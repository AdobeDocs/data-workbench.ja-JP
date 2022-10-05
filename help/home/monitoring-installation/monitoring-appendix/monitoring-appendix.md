---
description: このドキュメントでは、Data Workbench の監視プロファイルで使用されるフィールド、ディメンション、指標を使用したプロファイルについて説明します。
title: Data Workbench プロファイルのディメンションと指標
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench プロファイルのディメンションと指標{#data-workbench-profile-dimensions-and-metrics}

{{eol}}

このドキュメントでは、Data Workbench の監視プロファイルで使用されるフィールド、ディメンション、指標を使用したプロファイルについて説明します。

Data Workbench サーバーを監視するには、特定のサーバー情報も取得しながら、詳細なステータスを解析するスクリプトを使用してデータを収集します。 次に、Data Workbench サーバーの情報がページタグ呼び出しに渡され、Data Workbench Sensor が収集してVSLファイルに保存するようになります。

## Data Workbench監視プロファイルに使用されるプロファイル {#section-b5b1234f55c3407dae8e68b031b7cd7f}

これらのプロファイルは、サーバーの状態とパフォーマンスのデータを表示できるディメンションと指標を提供します。

* [Insight プロファイルステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Insight サーバーステータスプロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Insight Historic プロファイルのDimension](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight 履歴監視プロファイルの指標](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

ステータスプロファイルを使用すると、Data Workbench の現在の動作を、運用上の観点から確認できます。 この **プロファイルステータス** プロファイルと **サーバーステータス** プロファイルは、詳細なステータスと data workbench サーバーからデータを収集します。 収集されたすべてのデータは、 `cs-uri-query` フィールドを使用します。

この **過去のプロファイル** 履歴データを使用して、構成とハードウェアの変更が及ぼす影響を評価できます。 履歴プロファイルは、構成とハードウェアの変更が時間の経過と共に及ぼす影響を評価できるので、最も役に立つ場合があります。
