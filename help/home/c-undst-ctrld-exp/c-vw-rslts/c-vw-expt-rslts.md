---
description: 新しいフィールドを Log Processing.cfg に追加し、新しい Split 変換と拡張ディメンションを作成した後、データ再処理の Fast Input ステージが完了したら、作成した新しい拡張ディメンションを表示できます。
solution: Analytics
title: 実験結果の表示
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 実験結果の表示{#viewing-the-experiment-results}

{{eol}}

新しいフィールドを Log Processing.cfg に追加し、新しい Split 変換と拡張ディメンションを作成した後、データ再処理の Fast Input ステージが完了したら、作成した新しい拡張ディメンションを表示できます。

このディメンションは、デフォルトで、各実験グループのセッション数を表示します。

**実験ディメンションを表示するには**

* の任意のワークスペース内 [!DNL Insight]をクリックし、作成した experiment ディメンションを含むテーブルを開きます。

   実験ディメンション要素は、現在実行中の各実験と、各実験内の各グループを表し、各グループの現在のセッション数が表示されます。 各グループには、次の形式で実験名に続くグループ名を付けます。

   *実験名。グループ名*

   例：[!DNL New Homepage.Control]

次の表に、 [!DNL Transformation.cfg] そして各実験とそのグループ

新しいホームページの実験は、表の下部に、次の 2 つのグループと共に表示されます。コントロールとインデックス 2

![](assets/controlledexpgrps.png)

これで、実験ディメンションと関連する指標を使用して、実験結果を調べて解釈し、それらの結果を詳しく説明する有用なレポートを作成できます。
