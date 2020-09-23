---
description: 新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換と拡張ディメンションを作成した後で、データ再処理のFast Inputステージが完了したら、作成した新しい拡張ディメンションを表示できます。
solution: Analytics,Analytics
title: 実験結果の表示
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 4%

---


# 実験結果の表示{#viewing-the-experiment-results}

新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換と拡張ディメンションを作成した後で、データ再処理のFast Inputステージが完了したら、作成した新しい拡張ディメンションを表示できます。

このディメンションには、デフォルトで、各テストグループのセッション数が表示されます。

**テストディメンションを表示するには**

* の任意のワークスペース内 [!DNL Insight]で、作成したテストディメンションを含むテーブルを開きます。

   テストディメンション要素は、現在実行している各テストと各テスト内の各グループを表し、各グループの現在のセッション数と共に表示されます。 各グループには次の形式で名前が付けられ、テスト名の後にグループ名が続きます。

   *テスト名。グループ名*

   例：[!DNL New Homepage.Control]

次の表に、で作成された制御実験グループディメンション [!DNL Transformation.cfg] と、各実験とそのグループを示します。

新しいホームページのテストは、表の下部に2つのグループと共に表示されます。制御とインデックス2

![](assets/controlledexpgrps.png)

これで、テストディメンションや関連する指標を使用して、テスト結果を調べたり解釈したり、その結果を詳細に説明する有用なレポートを作成したりできます。
