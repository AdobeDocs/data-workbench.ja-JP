---
description: After you have added the new field to Log Processing.cfg and created the new Split transformation and extended dimension, you can view the new extended dimension that you created as soon as the Fast Input stage of data reprocessing has finished.
solution: Analytics
title: 実験結果の表示
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 実験結果の表示{#viewing-the-experiment-results}

新しいフィールドを Log Processing.cfg に追加し、新しい Split 変換と拡張ディメンションを作成した後、データ再処理の Fast Input ステージが完了したら、作成した新しい拡張ディメンションを表示できます。

このディメンションは、デフォルトで、各実験グループのセッション数を表示します。

**実験ディメンションを表示するには**

* の任意のワークスペース内 [!DNL Insight]をクリックし、作成した experiment ディメンションを含むテーブルを開きます。

   The experiment dimension elements, which represent each experiment you are currently running and each group within each experiment, display with the current number of sessions for each group. 各グループには、次の形式で実験名に続くグループ名を付けます。

   *実験名。グループ名*

   例：[!DNL New Homepage.Control]

次の表に、 [!DNL Transformation.cfg] そして各実験とそのグループ

The New Homepage experiment is shown at the bottom of the table with its two groups: Control and index2.

![](assets/controlledexpgrps.png)

これで、実験ディメンションと関連する指標を使用して、実験結果を調べて解釈し、それらの結果を詳しく説明する有用なレポートを作成できます。
