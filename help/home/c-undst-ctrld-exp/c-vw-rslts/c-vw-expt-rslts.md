---
description: 新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換および拡張ディメンションを作成したら、データ再処理のFast Inputステージが終了したら、作成した新しい拡張ディメンションを表示できます。
solution: Insight,Analytics
title: テスト結果の表示
topic: Data workbench
uuid: c0468cad-fb8d-4ecf-8912-bf80b44b0a65
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# テスト結果の表示{#viewing-the-experiment-results}

新しいフィールドをLog Processing.cfgに追加し、新しいSplit変換および拡張ディメンションを作成したら、データ再処理のFast Inputステージが終了したら、作成した新しい拡張ディメンションを表示できます。

このディメンションには、デフォルトで、各テストグループのセッション数が表示されます。

**テストディメンションを表示するには**

* の任意のワークスペース [!DNL Insight]内で、作成したテストディメンションを含むテーブルを開きます。

   実験ディメンション要素は、現在実行中の各実験と各実験内の各グループを表し、各グループの現在のセッション数と共に表示されます。 各グループには、次の形式で、テスト名とグループ名を使用して名前が付けられます。

   *テスト名。グループ名*

   次に例を示します。[!DNL New Homepage.Control]

次の表に、で作成された制御実験グループディメンションと、各実 [!DNL Transformation.cfg] 験とそのグループを示します。

新しいホームページのテストは、表の下部に2つのグループと共に表示されます。Controlとindex2。

![](assets/controlledexpgrps.png)

これで、テストディメンションと関連する指標を使用して、テスト結果を調べ、解釈し、その結果を詳細に説明する有用なレポートを作成できます。
