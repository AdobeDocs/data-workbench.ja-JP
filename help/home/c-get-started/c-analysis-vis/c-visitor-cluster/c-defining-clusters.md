---
description: 入力変数、クラスターの数およびターゲット母集団（必要に応じて）を選択して、データセット内のクラスターを定義します。
title: クラスターの構築
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 61%

---

# クラスターの構築{#building-clusters}

入力変数、クラスターの数およびターゲット母集団（必要に応じて）を選択して、データセット内のクラスターを定義します。

**クラスターの構築**

1.  **[!UICONTROL Cluster Builder]**.

   **ビジュアライゼーション**／**予測分析**／**クラスタリング**／**クラスタービルダー**&#x200B;をクリックします。

   ![](assets/cluster-builder-step1.png)

1. 入力変数を選択します。

   * ツールバーの&#x200B;**[!UICONTROL Metric]**&#x200B;メニューから「 」を選択して、**[!UICONTROL Input Variables]**&#x200B;リストに指標を追加します。

      ![](assets/cluster_metric_select.png)

   * ディメンションエレメントをDimensionのテーブルからドラッグして、**[!UICONTROL Input Variables]**&#x200B;リストに追加します。

      **[!UICONTROL Ctrl + Alt]**&#x200B;を押して、選択したディメンション要素を&#x200B;**[!UICONTROL Input Variables]**&#x200B;リストまたはツールバーの&#x200B;**[!UICONTROL Element]**&#x200B;ボックスにドラッグします。

      ![](assets/cluster_dim_select.png)
   デフォルトでは、データセット全体に対してクラスタリングが実行されます。左側の&#x200B;**[!UICONTROL Preprocessing]**&#x200B;ウィンドウにすべての入力変数が表示されます。
1. **[!UICONTROL Options]**&#x200B;メニューを使用して、目的のクラスタ数を選択します。

   ![](assets/build_cluster_2.png)

1. データセット内の訪問者数のサブセットをクラスター化する場合は、母集団フィルターを定義できます。

   ![](assets/build_cluster_3.png)

   まず、ワークスペース内の選択を使用して目的のサブセットを定義するか、**[!UICONTROL Filter Editor]**&#x200B;を使用します。 目的のサブセットを選択したら、**[!UICONTROL Options]**&#x200B;メニューで「ターゲット母集団」を設定します。 ターゲットグループにわかりやすい名前を付けることをお勧めします。

   **[!UICONTROL Options]**&#x200B;メニューには、パスの最大数と、中心収束の許容されるしきい値を制御する設定もあります。

1. 入力とオプションを設定したら、「**移動**」ボタンをクリックしてクラスタリングをローカルで実行するか、「**[!UICONTROL Submit]**」を押して予測分析サーバーにタスクを送信します。 サーバーに送信した場合は、収束が完了すると、データセットに結果のディメンションが保存されます。

   ローカルで実行した場合は、クラスタービルダーが 4 つキャノピークラスタリングステージを経て、入力に基づいてインテリジェントに中心が定義されます。

   クラスターの中心で指定された収束のしきい値を超える変更が停止されると、クラスターディメンションが収束し、クラスタービルダーに入力と各クラスターの関連についての追加情報が表示されます。

1. クラスターをカスタマイズします。

   統計のカラーバーを右クリックすると、コンテキストメニューが開き、関連性のしきい値をカスタマイズしたり、ディメンションエレメント分布の場合には、表示されるテストを選択したりできます。

   ![](assets/build_cluster_7.png)

   指標の入力は各クラスターに t 検定を提供し、ディメンションエレメントの入力は各クラスターに 3 つの分布検定（カイ二乗、エントロピー U 統計およびクラメールの V 統計）を提供します。

   >[!NOTE]
   >
   >収束中に入力を追加または削除すると、**Go**&#x200B;を再度押すまでプロセスは一時停止します。

   クラスターを作成したら、カラーピッカーを開いて、異なる配分結果に色を割り当てることができます。

   ![](assets/build_cluster_5.png)

1. クラスターディメンションが収束すると、普通にテーブルに指標を追加し、選択できます。また、エレメント名（クラスター 1、クラスター 2 など）を右クリックして、コンテキストメニューを開き、意味のある名前に変更できます。

   ![](assets/build_cluster_6.png)

1. 他のビジュアライゼーションでこのクラスターディメンションを使用する場合は、ローカルで&#x200B;**[!UICONTROL Save]**&#x200B;するか、**[!UICONTROL Submit]**&#x200B;サーバーに送信できます。

収束を再度実行する場合や、入力の関連性を確認する場合は、クラスタービルダーで既存のクラスターディメンションをロードすることもできます。

>[!TIP]
>
>選択すると、**[!UICONTROL Reset]**&#x200B;はすべての入力変数を完全に解放し、新しいクラスターを定義する空白のクラスタービルダービジュアライゼーションを提供します。
