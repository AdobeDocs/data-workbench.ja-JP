---
description: Data Workbenchプロファイルのステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する最新の情報を提供します。
title: Data Workbench のプロファイルステータスワークスペース
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench のプロファイルステータスワークスペース{#data-workbench-profile-status-workspace}

Data Workbenchプロファイルのステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する最新の情報を提供します。

## Data Workbenchプロファイルの状態{#section-65d1fa393cfd450cbacef3cba823fcc1}

このステータスプロファイルは、最新であるが、10分ごとにポーリングされ、レポートには常にこの10分の待ち時間が含まれるので、実際にはリアルタイムではないData Workbenchサーバー情報を提供します。 より正確には、このプロファイルが生成するデータセットは、エージェントからのサーバの最新の監視を提供します。ほとんどの場合、デフォルトのポーリング期間は10分です。

Data Workbenchプロファイルのステータスプロファイルで使用されるディメンションについて詳しくは、[Insightプロファイルのステータスプロファイル](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)を参照してください。

![](assets/Status_General_Status.png)

このレポートは、コンポーネントや特定のトラフィックの変動ではなく、運用の監視に役立ちます。

![](assets/Status_General_page.png)

これにより、誰がどのモードにいるかを把握できます。特定のプロファイルに対して高いFast Inputレートが表示される場合は、そのプロファイルはFast Inputモードになっています。

停止した指標が1の場合、サーバーは停止します。 値が0の場合、サーバーは停止しません。

**大規模なバッチ読み込みのログ読み取り**

![](assets/Status_General_stalled_log.png)
