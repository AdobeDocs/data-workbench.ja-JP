---
description: 指標、ディメンション、フィルターは、Data Workbench データセットへと処理されるデータに関する計算のフレームワークを提供します。
title: Data Workbench 指標、ディメンション、フィルター
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
exl-id: 687d9695-e70c-49ff-ac11-1537e6309e16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 87%

---

# Data Workbench 指標、ディメンション、フィルター{#data-workbench-metrics-dimensions-and-filters}

{{eol}}

指標、ディメンション、フィルターは、Data Workbench データセットへと処理されるデータに関する計算のフレームワークを提供します。

このフレームワークを使用して定義された計算の結果は、ワークスペース、ダッシュボード、レポート、その他の出力に表示されます。つまり、アプリケーション内またはアプリケーションから見える数値はすべて、指標、ディメンション、フィルターを伴う、データセットのクエリ結果です。

最も基本的なレベルでは、指標は計算元やデータセットについて記述し、ディメンションはデータセット内のデータをカテゴリに分類し、フィルターはデータセット内のデータの選択部分またはサブセットを記述します。

データのディメンションは、Data Workbench サーバーがデータを処理してデータセットを作成する際に作成されたあと、新しいデータがサーバーで読み取られ処理されるたびに更新されます。指標とフィルターは、データのこれらディメンションから計算されます。

>[!CAUTION]
>
>内部指標を再定義すると、誤った値が原因でシステムが予期しない動作をします。指標が 100% 読み取られない限り、レポートは生成されません。指標の定義を変更しないことをお勧めします。

## 例 {#section-ecc465d1a5e34d559c1983e96fa409ec}

世界中のすべての人々に関する情報を格納したデータセットがあるとしましょう。このデータセットには、少なくとも世界中のすべての人々とその年齢が含まれています。このデータセットから計算される有用な指標の 1 つとして、「Average Age（平均年齢）」が考えられます。この指標を評価すると、世界中の人々の平均年齢という 1 つの数値が得られます。

データセットにディメンションを追加すると、この情報の有用性と管理性が向上します。データセットに各人の居住国も含まれている場合は、「Country（国）」ディメンションを定義すると、世界の国ごとに人々をグループ分けすることができます。「Country」ディメンションに関して「Average Age」指標を評価すると、数値のリストが得られます。各数値は各国の人々の平均年齢を表します。

指標の数式でフィルター（選択フィルター）を適用すると、より詳細な情報を提供したり、既存の指標およびディメンションに基づいて新しい指標を定義したりできます。「国がスウェーデンに等しい」という意味のフィルターで「Average Age」指標を評価すると、スウェーデンの人々の平均年齢という 1 つの数値が得られます。このフィルターに基づく指標は、「Swedish Average Age（スウェーデンの平均年齢）」となります。

次に例を示します。

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## 指標、ディメンション、フィルターの関係 {#section-28622596124140b280e6b993b174ef84}

一般に、ディメンションに関して指標を評価すると、その指標はディメンション要素（または単に要素）ごとに評価されます。上の例では、「Country」ディメンションには、世界の国ごとに要素があります。「Country」に関して「Average Age」を評価すると、要素「Sweden」を含む各要素（国）の平均年齢が算出されます。

ディメンションに関して指標を評価する場合、ディメンション全体についてその指標を評価するか、特定のディメンション要素に対応するフィルターを定義するかに関係なく、特定のディメンション要素については同じ数値結果が得られることに注意してください。前述の例を使用すると、スウェーデンの人々の平均年齢を調べると、次のどちらの方法でも同じ結果が得られます。

* 「Country」ディメンションに関して「Average Age」指標を評価した後で、ディメンション要素「Sweden」の数値を調べる。
* 「スウェーデンの人々」をフィルターして「Average Age」指標を評価する ( [!DNL Average_Age[Country='Sweden']]) をクリックします。

フィルターは、1 つ以上のディメンションおよびディメンション要素を参照する、一定の構文で表現された式です。上の例のとおり、[!DNL [dimension=element]] という式を使用すると、フィルターを簡単に指定できます。

このようなフィルターを適用し、次のような式を使用して新しい指標を簡単に定義できます。 [!DNL New_Metric=Metric[Filter]]. このようなフィルターは、特定のディメンション要素に基づいて新しい指標を定義する場合に使用できます。上記の例を使用するには、 [!DNL Average_Age[Country='Sweden']]は、スウェーデンの人々の平均年齢を表す指標を示します。 この指標に「Swedish_Average_Age」のような名前を付けると、他の計算で指標として使用できます。例えば、[!DNL Swedish_Average_Age/Average_Age] を評価すると、スウェーデンの人々の平均年齢と全世界の人々の平均年齢の比率を示す 1 つの数値が得られます。

世界中のすべての人物に関する情報を含むデータセットに目の色ディメンションも含まれている場合、式 [!DNL Swedish_Average_Age[Eye_Color='green']] 緑の目をしたスウェーデン人の平均年齢を招くだろう また、異なるフィルターを適用すると、中間の指標定義を使用せずに同じ結果を得ることができます。 [!DNL Average_Age[Country='Sweden' AND Eye_Color='green']]. この場合、[!DNL AND] 演算子は、他の 2 つの基本フィルター式を使用して 1 つのフィルター式を指定する働きをします。
