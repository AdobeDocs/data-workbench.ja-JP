---
description: 通常、Data Workbenchサーバーは受信したユーザークエリに応答し、ユーザーが要求しなくなるまで、引き続き結果とリアルタイム更新を提供します。
solution: Analytics
title: クエリーキュー
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# クエリーキュー{#query-queue}

通常、Data Workbenchサーバーは受信したユーザークエリに応答し、ユーザーが要求しなくなるまで、引き続き結果とリアルタイム更新を提供します。

多くのData Workbenchユーザーを持つシステムでは、特に、アクティブなクエリーの数が、サーバーで使用できる量を超えるシステムリソースを必要とする場合があります。 [!DNL Query Queue] 回答を提供するために必要なリソースが使用可能になるまで、サーバーは一時的に一部のクエリを保留状態にできます。 The [!DNL Query Queue] also provides features to prioritize queries based on a variety of parameters, so that in case of resource contention, higher-priority queries are answered first.

単一のクライアントまたはレポートサーバーからのクエリーは、1 つのバンチに配置され、1 つの単位としてスケジュールされます。クエリーが使用する特定のシステムリソースの量を制限するように、リソースモニターを設定できます。モニタリング対象リソースが別のクエリーバンチのスケジューリングを許可すると、最も高い優先順位のバンチがスケジュールされます。リソース制限によってクエリーがまだスケジュールされていないユーザーには、エラーは表示されませんが、クエリーがキューに格納済みであることが通知されるので、ローカルサンプルに対して作業を続けられます。

The default configuration includes a simple configuration for the [!DNL Query Queue], but leaves it disabled. Administrators can enable or disable the [!DNL Query Queue], configure resource monitors to determine how much of various resources are used for querying, and configure complex prioritization policies for different users.

**Server.cfgファイルを[!DNL Query Queuing]**

1. //をク [!DNL Server.cfg] リックし **[!UICONTROL Admin]** て開 **[!UICONTROL Profile Manager]** きます **[!UICONTROL Dataset]**。
1. **[!UICONTROL Server.cfg]** を右クリックし、編集用にローカル化します。
1. 展開 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 次のパラメーターを設定します。

   * **User Groups：**&#x200B;ポリシー、ユーザー、キューの優先順位を設定できます。定義については「[クエリーキューのユーザーグループ](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)」を参照してください。

   * **アクティブ：** （ベクトル）を有効または無効にしま [!DNL Query Queue]す。 有効な値は true または false です。デフォルト設定は false です。

   * **Default User Group：**（String）どのユーザーグループにもリストされていない場合、ユーザーを追加するユーザーグループの名前を入力します。
   * **Resource Monitors：**（Vector）右クリックしてリソースモニターを追加します。You can specify whether the [!DNL Query Queue] monitors memory or the number of queries. 「**[!UICONTROL Resource Monitor]**」を右クリックして、「Memory Budget Monitor」または「Number of Queries Monitor」を選択します。See [Query Queue Resource Monitors](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) for more information.

   * **Untouchable Priority：**（Int）この値以上の優先順位を持つバンチが、より優先順位が高いバンチのスケジューリングを妨げないようにします。「ユーザグループパラメータ」 [!DNL Memory Budget Monitor] の表で説明され [ていると共に使用されます](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)。

