---
description: 通常、Data Workbenchサーバーは受信したユーザークエリに対して回答し、ユーザーが要求しなくなるまで結果とリアルタイム更新を提供し続けます。
title: クエリキュー
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 48%

---

# クエリキュー{#query-queue}

{{eol}}

通常、Data Workbenchサーバーは受信したユーザークエリに対して回答し、ユーザーが要求しなくなるまで結果とリアルタイム更新を提供し続けます。

特に多くのData Workbenchユーザーを持つシステムでは、アクティブなクエリの数が、サーバーで使用できるよりも多くのシステムリソースを必要とする場合があります。 [!DNL Query Queue] では、回答を提供するために必要なリソースが利用可能になるまで、サーバーは一部のクエリを一時的に保留状態にすることができます。 この [!DNL Query Queue] また、様々なパラメータに基づいてクエリを優先順位付けする機能も提供され、リソースの競合時には、優先度の高いクエリが最初に回答されます。

単一のクライアントまたはレポートサーバーからのクエリーは、1 つのバンチに配置され、1 つの単位としてスケジュールされます。クエリーが使用する特定のシステムリソースの量を制限するように、リソースモニターを設定できます。モニタリング対象リソースが別のクエリーバンチのスケジューリングを許可すると、最も高い優先順位のバンチがスケジュールされます。リソース制限によってクエリーがまだスケジュールされていないユーザーには、エラーは表示されませんが、クエリーがキューに格納済みであることが通知されるので、ローカルサンプルに対して作業を続けられます。

デフォルトの設定には、 [!DNL Query Queue]に設定されるが、無効のままになる。 管理者は、 [!DNL Query Queue]では、クエリに使用される様々なリソースの量を決定するためにリソースモニターを設定し、異なるユーザーに対して複雑な優先順位付けポリシーを設定します。

**の Server.cfg ファイルを設定するには、以下を実行します。[!DNL Query Queuing]**

1. 開く [!DNL Server.cfg] クリックして **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. **[!UICONTROL Server.cfg]** を右クリックし、編集用にローカル化します。
1. 展開 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 次のパラメーターを設定します。

   * **User Groups：**&#x200B;ポリシー、ユーザー、キューの優先順位を設定できます。定義については「[クエリーキューのユーザーグループ](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)」を参照してください。

   * **アクティブ：** (Vector) [!DNL Query Queue]. 有効な値は true または false です。デフォルト設定は false です。

   * **Default User Group：**（String）どのユーザーグループにもリストされていない場合、ユーザーを追加するユーザーグループの名前を入力します。
   * **Resource Monitors：**（Vector）右クリックしてリソースモニターを追加します。次の項目を指定して、 [!DNL Query Queue] メモリまたはクエリ数を監視します。 「**[!UICONTROL Resource Monitor]**」を右クリックして、「Memory Budget Monitor」または「Number of Queries Monitor」を選択します。詳しくは、 [クエリキューのリソースモニター](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) を参照してください。

   * **Untouchable Priority：**（Int）この値以上の優先順位を持つバンチが、より優先順位が高いバンチのスケジューリングを妨げないようにします。と組み合わせて使用され、 [!DNL Memory Budget Monitor] 以下に記載されている [ユーザーグループパラメータの表](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
