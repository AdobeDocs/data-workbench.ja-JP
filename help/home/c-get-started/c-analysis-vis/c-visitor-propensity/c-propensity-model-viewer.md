---
description: モデルビューアでは、傾向スコアリング機能を使用して、ロジスティック回帰モデルを生成できます。
title: モデルビューア
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

---

# モデルビューア{#model-viewer}

モデルビューアでは、傾向スコアリング機能を使用してロジスティック回帰モデルを生成できます。

モデルビューアでは、（定数項を含む）各入力変数の係数の重みとその統計的な誤差範囲が表示されます。高い絶対係数と小さな誤差の許容範囲を示す入力変数は、モデルの中で最も重要な予測因子です。

**モデルビューアグラフを開くには**

1. [!DNL Add Visualization > Predictive Analytics > Scoring] を選択します。
1. 保存されたスコアの「モデル完了」の上にカーソルを置きます。

![](assets/propensity_model_viewer.png)

係数 >= 1 の入力変数は傾向モデルにプラスの影響を与えます。係数 &lt; 1 は傾向モデルにマイナスの影響を与えます。括弧内に定義される範囲は誤差で、成功した母集団における入力変数の整合性を示します。
