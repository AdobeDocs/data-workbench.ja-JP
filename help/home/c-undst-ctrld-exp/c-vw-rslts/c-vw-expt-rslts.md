---
description: 新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換と拡張ディメンションを作成した後、データ再処理のFast Inputステージが完了したら、作成した新しい拡張ディメンションを表示できます。
solution: Analytics,Analytics
title: 実験結果の表示
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
exl-id: cada693c-79cb-4f49-a2f0-6ff60425be1c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---

# 実験結果の表示{#viewing-the-experiment-results}

新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換と拡張ディメンションを作成した後、データ再処理のFast Inputステージが完了したら、作成した新しい拡張ディメンションを表示できます。

このディメンションは、デフォルトで、各実験グループのセッション数を表示します。

**実験ディメンションを表示するには**

* [!DNL Insight]のワークスペース内で、作成した実験ディメンションを含むテーブルを開きます。

   現在実行中の各実験と、各実験内の各グループを表す実験ディメンション要素が、各グループの現在のセッション数と共に表示されます。 各グループには、実験名の後にグループ名を付けた、次の形式で名前が付けられます。

   *Experiment Name.Group Name*

   例：[!DNL New Homepage.Control]

次の表に、[!DNL Transformation.cfg]で作成された対照実験グループディメンションと、各実験とそのグループを示します。

新しいホームページの実験は、表の下部に2つのグループと共に表示されます。コントロールとインデックス2

![](assets/controlledexpgrps.png)

これで、実験ディメンションと関連指標を使用して、実験結果を調査および解釈し、その結果を詳しく説明する有用なレポートを作成できます。
