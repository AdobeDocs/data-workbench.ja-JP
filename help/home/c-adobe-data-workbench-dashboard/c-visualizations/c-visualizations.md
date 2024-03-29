---
description: ビジュアライゼーションは、ダッシュボードキャンバスに追加される要素で、様々な指標やディメンションベースのデータを表示するように設定されます。
title: ビジュアライゼーション
uuid: 1e15de30-7761-422a-a836-7a1b49b58daf
exl-id: 7e8b23cd-5e95-4cd5-b07e-3aa53f26fac7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 3%

---

# ビジュアライゼーション{#visualizations}

{{eol}}

ビジュアライゼーションは、ダッシュボードキャンバスに追加される要素で、様々な指標やディメンションベースのデータを表示するように設定されます。

すべてのダッシュボードは、1 つ以上のビジュアライゼーションで構成されます。 各ビジュアライゼーションは、ダッシュボードキャンバス上の他のすべてのビジュアライゼーションとは独立して、作成、削除、サイズ変更および再設定が可能です。

また、ビジュアライゼーションはインタラクティブで、ビジュアライゼーション内の 1 つ以上のデータ要素に選択を加えることで、データをすばやくセグメント化できます。 あるビジュアライゼーション内での選択により、キャンバス上の他のビジュアライゼーションにリアルタイムでフィルターが動的に適用されます。 これにより、キャンバス上のすべてのビジュアライゼーションで同じデータがレンダリングされます。

ビジュアライゼーションには、8 つの異なるタイプがあります。 各指標は、他のビジュアライゼーションとは独立して、追加、サイズ変更、設定および削除できます。 ビジュアライゼーションには、Data Workbench アーキテクトが Data Workbench で定義したデータが表示されます。

使用できるビジュアライゼーションには、次の 8 種類があります。

* 縦棒グラフ
* 棒グラフ
* 折れ線グラフ
* テーブル
* 指標の凡例
* 円グラフ
* 散布グラフ
* リッチテキスト

## ビジュアライゼーションユーザーインターフェイス {#section-54a73865f00742268340cf9123d6c590}

ビジュアライゼーションのヘッダー部分には、ビジュアライゼーションのタイトルとビジュアライゼーションツールが含まれます。このタイトルは、ビジュアライゼーションのタイプと状態に応じて変わります。 ビジュアライゼーションの本文にはコンテンツが含まれ、表示されるビジュアライゼーションのタイプと設定に応じて異なります。 ビジュアライゼーションツールは、マウスがビジュアライゼーションウィンドウに入ったときにのみ表示されます。 それ以外の場合は、非表示になります。

![](assets/visualization.png)

* ビジュアライゼーションのタイトル。 このビジュアライゼーションについて説明します。 タイトルは自動的に生成されるか、カスタムタイトルで手動で上書きされます。
* 表示された金額。 視覚化するディメンションについて、は、表示されるデータの量と使用可能な合計量を表示します。
* サンプルインジケータ。 視覚化されたデータが 100%完了のクエリ結果ではなく、サンプルの場合に表示されます。
* ビジュアライゼーションツール ビジュアライゼーションに対して特定の操作を実行します。 使用できるツールは、ビジュアライゼーションの種類、状態、現在のユーザー権限によって異なります。
* ビジュアライゼーション本文。 設定に従ってビジュアライゼーションのデータを表示します。 この領域はインタラクティブで、表示されるビジュアライゼーションの種類に応じて異なります。
