---
description: 通常、Data Workbenchサーバは、受信したユーザクエリに応答し、ユーザが要求しなくなるまで、結果とリアルタイム更新を提供し続けます。
title: クエリキュー
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 48%

---

# クエリキュー{#query-queue}

通常、Data Workbenchサーバは、受信したユーザクエリに応答し、ユーザが要求しなくなるまで、結果とリアルタイム更新を提供し続けます。

多数のData Workbenchユーザーを持つシステムでは特に、アクティブなクエリの数が、サーバーで使用できる量を超えるシステムリソースを必要とする場合があります。 [!DNL Query Queue] 一部のクエリを一時的に保留し、回答に必要なリソースが使用可能になるまで保留できます。[!DNL Query Queue]は、様々なパラメーターに基づいてクエリに優先順位を付ける機能も備えているので、リソース競合時には、優先順位の高いクエリが最初に回答されます。

単一のクライアントまたはレポートサーバーからのクエリーは、1 つのバンチに配置され、1 つの単位としてスケジュールされます。クエリーが使用する特定のシステムリソースの量を制限するように、リソースモニターを設定できます。モニタリング対象リソースが別のクエリーバンチのスケジューリングを許可すると、最も高い優先順位のバンチがスケジュールされます。リソース制限によってクエリーがまだスケジュールされていないユーザーには、エラーは表示されませんが、クエリーがキューに格納済みであることが通知されるので、ローカルサンプルに対して作業を続けられます。

デフォルトの設定には[!DNL Query Queue]の単純な設定が含まれていますが、無効のままです。 管理者は、[!DNL Query Queue]を有効または無効にしたり、クエリに使用する様々なリソースの量を決定するようリソースモニターを設定したり、様々なユーザーに対して複雑な優先順位付けポリシーを設定したりできます。

**Server.cfgファイルを[!DNL Query Queuing]**

1. [!DNL Server.cfg]を開くには、**[!UICONTROL Admin]**/**[!UICONTROL Profile Manager]**/**[!UICONTROL Dataset]**&#x200B;をクリックします。
1. **[!UICONTROL Server.cfg]** を右クリックし、編集用にローカル化します。
1. 展開 [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. 次のパラメーターを設定します。

   * **User Groups：**&#x200B;ポリシー、ユーザー、キューの優先順位を設定できます。定義については「[クエリーキューのユーザーグループ](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)」を参照してください。

   * **Active:** (Vector)を有効または無効にし [!DNL Query Queue]ます。有効な値は true または false です。デフォルト設定は false です。

   * **Default User Group：**（String）どのユーザーグループにもリストされていない場合、ユーザーを追加するユーザーグループの名前を入力します。
   * **Resource Monitors：**（Vector）右クリックしてリソースモニターを追加します。[!DNL Query Queue]でメモリを監視するか、クエリ数を監視するかを指定できます。 「**[!UICONTROL Resource Monitor]**」を右クリックして、「Memory Budget Monitor」または「Number of Queries Monitor」を選択します。詳しくは、[クエリキューのリソースモニター](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325)を参照してください。

   * **Untouchable Priority：**（Int）この値以上の優先順位を持つバンチが、より優先順位が高いバンチのスケジューリングを妨げないようにします。[ユーザーグループパラメーターテーブル](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)で説明されている[!DNL Memory Budget Monitor]と組み合わせて使用します。
