---
description: Data Workbenchのプロファイルステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する現在の情報を提供します。
solution: Analytics
title: Data Workbenchのプロファイルステータスワークスペース
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbenchのプロファイルステータスワークスペース{#data-workbench-profile-status-workspace}

Data Workbenchのプロファイルステータスプロファイルは、サーバー指標や履歴データではなく、プロファイルに基づいて、Data Workbenchサーバーの正常性に関する現在の情報を提供します。

## Data Workbenchのプロファイルステータス {#section-65d1fa393cfd450cbacef3cba823fcc1}

このステータスプロファイルは、最新ではあるが、リアルタイムではないData Workbenchサーバー情報を提供します。エージェントは10分ごとにポーリングされ、レポートには常にこの10分の待ち時間が含まれるからです。 より正確には、このプロファイルによって生成されるデータセットは、エージェントからのサーバの最新の監視を提供します。ほとんどの場合、デフォルトのポーリング期間は10分です。

Data Workbenchのプロファイルステータスプロファイルで使用されるディメンションに関するその他の参照情報については、 [Insight Profile Statusプロファイルを参照してくださ](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)い。

![](assets/Status_General_Status.png)

このレポートは、コンポーネントや特定のトラフィックの変動ではなく、操作を監視する場合に便利です。

![](assets/Status_General_page.png)

これにより、誰がどのモードかがわかります。特定のプロファイルに対して高いFast Input率が表示される場合は、そのプロファイルはFast Inputモードになります。

停止した指標が1の場合、サーバーは停止します。 値が0の場合、サーバーは停止しません。

**大量のバッチ読み込みのログ読み取り**

![](assets/Status_General_stalled_log.png)

