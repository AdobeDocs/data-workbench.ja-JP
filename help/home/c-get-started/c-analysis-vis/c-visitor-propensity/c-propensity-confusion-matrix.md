---
description: 傾向スコアリングの統計的計算を定義しています。
title: 傾向スコアリングの計算
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 100%

---

# 傾向スコアリングの計算{#calculating-propensity-scoring}

傾向スコアリングの統計的計算が定義されています。

概念上、各訪問者に対して計算されたスコアは、指定されたイベント（ターゲットフィルターで定義）が発生するおよその確率です。したがって、スコアの値は、0 ～ 100％の範囲です。スコアリングの手順では、既存のサンプルをトレーニングデータとして使用して、イベントの確率と選択した関心のある独立変数の間の関係を見つけます。

数学的には、そうした関係は、各独立変数に対して関連付けられた各定量値に反映されます。これらの値は、モデル係数と呼ばれます。ScoreDim は、現在、反復再重み付け最小二乗（IRLS）アルゴリズムを使用してモデル係数を推定しています。IRLS は、現在のパスと前回のパスの間の係数の違いが 1.0e-6 未満になるまで（この時点を&#x200B;**収束した**&#x200B;と呼びます）、サンプルを複数回調査します。ただし、データによっては、IRLS は、収束に到達しない可能性があります。

この場合、モデルトレーニングの反復が終了するのは、次のときです。

* 係数の違いが小さくならずに大きくなる
* 1,000 パスに到達する
* 数学的エラーによって反復を継続できなくなる

IRLS が収束しない場合、確率的勾配降下法（SGD）と呼ばれるバックアップアルゴリズムが使用されます。SGD もまた、トレーニングサンプルを複数回調査します。ただし、IRLS とは異なり、反復の間の違いが常に指数関数的に減少するように、SGD のモデル係数が制御されます。同様に、SGD は、係数の違いが 1.0e-6 を下回るか 100,000 パスに到達すると終了します。IRLS の失敗と SGD の使用は、トレースログに記録されます。

両方のアルゴリズムでは、すべてのサンプルがモデルトレーニングに使用されるわけではありません。現在、サンプルの 80％がモデルのトレーニングに使用されます。モデルのトレーニングの終了後、残りの 20％のサンプルは、混同行列から計算された正解率、再現率、精度の観点から、モデルの強度を評価するのに使用されます。100％に近いほど、よいスコアリングモデルです。
