---
description: クラスタービルダーには、優先クラスター生成処理の中心を見つけるためのより高速な手法を使用する KMeans++ アルゴリズム（以前は KMeans アルゴリズムのみがサポートされていました）が含まれるようになりました。
title: Clustering 2.0
uuid: 14462bd3-06d1-4622-a2d8-f96aadb357f3
exl-id: 6a779ddc-c8f1-4c55-9c17-1119fe1aa791
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 87%

---

# Clustering 2.0{#clustering}

{{eol}}

クラスタービルダーには、優先クラスター生成処理の中心を見つけるためのより高速な手法を使用する KMeans++ アルゴリズム（以前は KMeans アルゴリズムのみがサポートされていました）が含まれるようになりました。

## K 平均法アルゴリズム {#section-92383a1be1d6402c95a25c902e90b850}

内 [クラスタービルダー](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/visitor-cluster/c-visitor-cluster.html?lang=en)を選択し、 **[!UICONTROL Options]** > **[!UICONTROL Algorithm]** ：クラスターを定義する際にアルゴリズムを選択します。

* **[!UICONTROL KMeans]**&#x200B;に移動します。このアルゴリズムでは、キャノピークラスターリングを使用して、クラスターの中心を定義します。
* **[!UICONTROL KMeans++]**&#x200B;に移動します。このアルゴリズムでは、大量のデータセットに対して実行した場合に、クラスターが迅速に構築されます。

<!-- <a id="section_8193A6D60C5540BB985085BE670B4544"></a> -->

KMeans++ は、KMeans クラスタリングアルゴリズムの強化実装で、k 個の初期中心をより適切に初期化します（元の KMeans アルゴリズムでは、初期中心がランダムに選択されます）。KMeans++ では、最初の中心がランダムに選択されます。残り k-1 個の中心は、データポイントと最も近い既存の中心との距離に基づいて 1 つずつ選択されます。最も遠いデータポイントは、近くのデータポイントよりも、新しい中心として選択される可能性が高くなります。初期中心を選択した後は、元の KMeans クラスタリングとまったく同じ処理が実行されます。

KMeans++ のワークフローは、クラスタービルダーで&#x200B;**オプション**／**アルゴリズム**／**KMeans++** を選択する必要がある以外、KMeans クラスタリングのワークフローとまったく同じです。

>[!NOTE]
>
>各 DPU は、独自のデータ部分に対して独自の KMeans++プロシージャを実行します。 DPU に利用可能なメモリが十分にある場合（割合は PAServer.cfg ファイルで設定できます）、必要な変数のデータをメモリに読み込みます。最初の中心のうち残りの k-1 個の選択と収束するまでの反復は、すべてメモリ内で実行されます。これにより、以前の K 平均法クラスタリングよりも速く実行されます。
