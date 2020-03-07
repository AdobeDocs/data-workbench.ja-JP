---
description: 入力変数、クラスターの数およびターゲット母集団（必要に応じて）を選択して、データセット内のクラスターを定義します。
solution: Analytics
title: クラスターの構築
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# クラスターの構築{#building-clusters}

入力変数、クラスターの数およびターゲット母集団（必要に応じて）を選択して、データセット内のクラスターを定義します。

**クラスターの構築**

1.  **[!UICONTROL Cluster Builder]**.

   **ビジュアライゼーション**／**予測分析**／**クラスタリング**／**クラスタービルダー**&#x200B;をクリックします。

   ![](assets/cluster-builder-step1.png)

1. 入力変数を選択します。

   * Add metrics to the **[!UICONTROL Input Variables]** list by selecting from the **[!UICONTROL Metric]** menu in the toolbar.

      ![](assets/cluster_metric_select.png)

   * Add dimension elements to the **[!UICONTROL Input Variables]** list by dragging them from a Dimension&#39;s table.

      Press **[!UICONTROL Ctrl + Alt]** and drag selected dimension elements to the **[!UICONTROL Input Variables]** list or to the **[!UICONTROL Element]** box in the toolbar.

      ![](assets/cluster_dim_select.png)
   デフォルトでは、データセット全体に対してクラスタリングが実行されます。You can see all input variables in the left **[!UICONTROL Preprocessing]** pane.
1. Use the **[!UICONTROL Options]** menu to select the desired number of clusters.

   ![](assets/build_cluster_2.png)

1. データセット内の訪問者数のサブセットをクラスター化する場合は、母集団フィルターを定義できます。

   ![](assets/build_cluster_3.png)

   Start by defining the desired subset using selections in your Workspace or by using the **[!UICONTROL Filter Editor]**. Once you have the desired subset selected, set the Target Population in the **[!UICONTROL Options]** menu. ターゲットグループにわかりやすい名前を付けることをお勧めします。

   The **[!UICONTROL Options]** menu also has settings to control the maximum number of passes and the acceptable threshold for center convergence.

1. After inputs and options have been configured, click the **Go** button to run the clustering locally or press **[!UICONTROL Submit]** to send the task to the Predictive Analytics Server. サーバーに送信した場合は、収束が完了すると、データセットに結果のディメンションが保存されます。

   ローカルで実行した場合は、クラスタービルダーが 4 つキャノピークラスタリングステージを経て、入力に基づいてインテリジェントに中心が定義されます。

   クラスターの中心で指定された収束のしきい値を超える変更が停止されると、クラスターディメンションが収束し、クラスタービルダーに入力と各クラスターの関連についての追加情報が表示されます。

1. クラスターをカスタマイズします。

   統計のカラーバーを右クリックすると、コンテキストメニューが開き、関連性のしきい値をカスタマイズしたり、ディメンションエレメント分布の場合には、表示されるテストを選択したりできます。

   ![](assets/build_cluster_7.png)

   指標の入力は各クラスターに t 検定を提供し、ディメンションエレメントの入力は各クラスターに 3 つの分布検定（カイ二乗、エントロピー U 統計およびクラメールの V 統計）を提供します。

   >[!NOTE]
   >
   >If you add or remove inputs during convergence, the process will pause until you press **Go** again.

   クラスターを作成したら、カラーピッカーを開いて、異なる配分結果に色を割り当てることができます。

   ![](assets/build_cluster_5.png)

1. クラスターディメンションが収束すると、普通にテーブルに指標を追加し、選択できます。また、エレメント名（クラスター 1、クラスター 2 など）を右クリックして、コンテキストメニューを開き、意味のある名前に変更できます。

   ![](assets/build_cluster_6.png)

1. If you wish to use this cluster dimension in other visualizations, you can **[!UICONTROL Save]** it locally or **[!UICONTROL Submit]** it to the server.

収束を再度実行する場合や、入力の関連性を確認する場合は、クラスタービルダーで既存のクラスターディメンションをロードすることもできます。

>[!TIP]
>
>When selected, **[!UICONTROL Reset]** will completely release all the input variables and give you a blank cluster builder visualization to define new clusters.

