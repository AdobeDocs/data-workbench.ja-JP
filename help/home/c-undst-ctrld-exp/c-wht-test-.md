---
description: 結果に基づいて大規模なドルの意思決定を行う自信を持てるように、テスト結果は明確で意味のあるものにする必要があります。
solution: Analytics
title: テスト対象
uuid: 9dfe3685-885e-4098-ab1d-ac891ccc5199
exl-id: 0f06ff0f-b385-4614-8007-afdb85191a85
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 1%

---

# テスト対象{#what-should-i-test}

結果に基づいて大規模なドルの意思決定を行う自信を持てるように、テスト結果は明確で意味のあるものにする必要があります。

様々なページレイアウトを [!DNL Sensor] また、サイト、Adobeは、貴社の Web サイトやビジネスに対して設定した目標に対応する、価値の高い戦略的なビジネスイニシアチブ、新規または再設計された Web サイト機能のテストに重点を置くことを示します。 最適な価格保証、パーソナライゼーション機能、マーケットオファー（パッケージやバンドルなど）、クリエイティブデザイン、アプリケーションプロセスなどの問題をテストできます。

対照実験を開発する際には、次の概念が最も重要です。

* **適切な変更を理解します。** これには、Web サイトの機能と、フロントエンド Web サイトの基盤となるビジネスプロセスに関する調査が必要です。 最も大きな影響を与え、容易にテストできる変更を加えたい。
* **小規模な変更は、大きな影響を与える可能性があります。** ビジネスに大きな影響を与えるために、テストするすべての変更を思い切って行う必要はありません。 常に小さな変更を行うことを自由にしますが、非常に重要な変更を行う。

## サポートされる方法 {#section-1071adaf54c64ba9bc5ef228c4a23635}

Site を使用して、様々な目標を持つ多くのタイプの実験を実行できます。 次のリストは、いくつかの例を示しています。

* ページ、コンテンツ、Web サイトのプロセスを変更して、コンバージョン率を向上させる。
* マーケティングキャンペーン、プロモーション、クロスセルおよびアップセルの変更による売上高の増加。
* ページの読み込み時間を変化させ、顧客のサービス品質とインフラストラクチャのパフォーマンスの実際の価値を把握します。

これらの目標を達成するために、Site は、以下のタイプの対照実験およびテスト方法をサポートしています。

* **ページの置換：** 静的 URL X を静的 URL Y に置き換えます。この方法は、動的環境での使用が制限されています。
* **動的な URI の置換：** これはページ置き換えのバリアントで、静的ページ X を動的ページ Y に置き換えて、動的コンテンツをレンダリングするために使用します。
* **オブジェクトの置換：** 固定オブジェクト X を固定オブジェクト Y に置き換えます。
* **コンテンツの置換：** コンテンツセット X（複数のオブジェクト、ページ、テーブルなど）をコンテンツセット Y に置き換えます。
* **実験変数の置換：** JavaScript object /writeCookie_X.jsを JavaScript object /writeCookie_Y.jsに置き換えて、特定のコンテンツを提供するためにバックエンドシステムで使用できる Cookie を記述します。

>[!NOTE]
>
>対照実験は、クエリー文字列の置き換えではなく、URI の置き換えに基づいています。 次の例では、特定の URL 内の URI が強調表示されています。
>
>`https://www.omniture.com/index.asp?id=1`
>
>例えば、対照実験では、コントロール母集団の URI を指定できます [!DNL index.asp] テストグループ URI に置き換えられる [!DNL index2.asp] を使用して、どのページデザインがより多くの価値を生み出すかを判断します。
