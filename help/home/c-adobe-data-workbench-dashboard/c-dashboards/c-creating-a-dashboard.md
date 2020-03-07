---
description: 短期的なAd Hoc Analyticalのニーズに対しても、ダッシュボードの作成をお勧めします。
solution: Analytics
title: ダッシュボードの作成
topic: Data workbench
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ダッシュボードの作成{#creating-a-dashboard}

短期的なAd Hoc Analyticalのニーズに対しても、ダッシュボードの作成をお勧めします。

>[!NOTE]
>
>読み取り専用ユーザーはダッシュボードを作成できません。 この節は、通常のユーザーおよび管理者のみに適用されます。

ダッシュボードの作成は、次のような理由で行うことができます。

* 新しいダッシュボードは、ダッシュボードを再利用したり共有したりする目的もなく、オンザフライでの分析用に一から開始できます。
* 保存して再利用するが共有しない個人分析を実行する目的で、新しいダッシュボードを作成できます。
* 新しいダッシュボードを作成、保存、共有し、そのダッシュボードの他のユーザーと共有してアクセスできます。 どのような場合でも、各シナリオは同じ時点から開始されます。空白のダッシュボードキャンバス。

>[!NOTE]
>
>ダッシュボードの構築を開始する前に、クエリーの割合を10%や25%など低い割合に減らすことをお勧めします。 これにより、完全なクエリを実行するよりも、Data Workbenchからデータのサンプルを非常に迅速に取り込むことができます。 これらのサンプル結果はより速く返されるので、ダッシュボードと分析をフレームアウトしながら、理想的な応答性を提供します。 クエリーを実行して完了する準備が整ったら、クエリー対象パラメーターを100%に更新できます。 クエリーの完了を調整する方法については、「クエ [リー対パラメーター」を参照してくださ](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323)い。

新しいダッシュボードを作成するには、[ダッシュボ **[!UICONTROL New]** ード]メニューの下のを選択します。

![](assets/new_dashboard.png)

分析ニーズに基づいてビジュアライゼーションを追加し、設定できる空のダッシュボードキャンバスが表示されます。 作業中は、保存するまでサーバー上では何も更新されません。

次に、表示するデータの種類と表示方法を決定します。 一般に、テーブルのビジュアライゼーションを使用して生データを表示し、それに合わせて他のグラフを作成するのに役立ちます。 ビジュアライゼーションを追加および設定する方法について詳しくは、ビジュアライゼーションの作成を [参照してくださ](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf)い。 ビジュアライゼーションを追加して設定し、ダッシュボードを構築した後、最終的には次のようになります。

![](assets/after_configure.png)

この時点から、分析を実行してダッシュボードを破棄するか、再利用や共有のためにダッシュボードをサーバに保存するかを選択できます。 ダッシュボードを操作して分析を実行する方法について詳しくは、ダッシュボード内での選択 [の実行に関する節を参照してください](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4)。