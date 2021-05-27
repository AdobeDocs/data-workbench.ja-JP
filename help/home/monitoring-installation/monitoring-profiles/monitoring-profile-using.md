---
description: Data Workbenchのプロファイルステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する現在の情報を提供します。
title: Data Workbench のプロファイルステータスワークスペース
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench のプロファイルステータスワークスペース{#data-workbench-profile-status-workspace}

Data Workbenchのプロファイルステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する現在の情報を提供します。

## Data Workbenchプロファイルのステータス{#section-65d1fa393cfd450cbacef3cba823fcc1}

このステータスプロファイルは、最新であるが、エージェントが10分ごとにポーリングされ、レポートには常にこの10分の遅延が含まれるので、非常にリアルタイムではないData Workbenchサーバー情報を提供します。 より正確に言うと、このプロファイルで生成されるデータセットは、エージェントからのサーバの最新の監視を提供します。ほとんどの場合、この監視はデフォルトのポーリング期間が10分です。

Data Workbenchのプロファイルステータスプロファイルで使用されるディメンションに関する追加のリファレンス情報については、[Insightのプロファイルステータスプロファイル](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)を参照してください。

![](assets/Status_General_Status.png)

このレポートは、コンポーネントや特定のトラフィックの変動ではなく、運用の監視に適しています。

![](assets/Status_General_page.png)

これにより、誰がどのモードになっているかがわかります。特定のプロファイルに対して高いFast Inputレートが表示される場合、そのプロファイルはFast Inputモードになります。

停止指標が1の場合、サーバーは停止します。 値が0の場合、サーバーは停止しません。

**大規模なバッチ読み込みのログ読み込み**

![](assets/Status_General_stalled_log.png)
