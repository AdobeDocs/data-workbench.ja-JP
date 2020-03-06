---
description: 傾向スコアリングでは、コンバージョンが発生する可能性や指定したイベントが完了する可能性を基に顧客を定義できます。傾向スコアリングを使用すると、プロセスを実行したり、キャンペーンを展開したりする前に、取り組みの潜在的な効果を最大限に引き出すことができます。
solution: Analytics
title: 傾向スコアリング
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 傾向スコアリング{#propensity-scoring}

傾向スコアリングでは、コンバージョンが発生する可能性や指定したイベントが完了する可能性を基に顧客を定義できます。傾向スコアリングを使用すると、プロセスを実行したり、キャンペーンを展開したりする前に、取り組みの潜在的な効果を最大限に引き出すことができます。

## 傾向スコアリングの価値 {#section-c51ece66effc42de9b754f0f46027c1b}

傾向スコアリングでは、データ検出を実行して、隠れた行動やデータ全体に存在するパターンを特定できます。具体的には、単純なセグメント化やフィルターよりも焦点を絞った客観的な手段を使用して、類似した顧客のクラスターを特定することができます。また、予測機能を設定して、価値の高い顧客の行動を把握することもできます。

高価値顧客を特定すると、顧客を魅了して最大限の効果を得ることができます。例えば、B2B 企業なら、リードへの営業訪問によってリードにスコアを付け、オフラインでコンバージョンに至る可能性を特定できます。すべてのリードはコストを増加させるので、販売をコンバージョンできる確率が最も高い見込み顧客を特定するインセンティブを作成することが、リソースを絞り込む最も効果的で最も安価な方法です。

傾向スコアリングを使用すると、特定のスコアの予測に最も役立つそうした要因を特定することや、イベントが発生する確率を高めることができますが、具体的な質問に回答する場合にも適用できます。そうした質問には、顧客がコンバージョンするか、顧客が電子メールに反応するか、顧客が再度購入するか、などがあります。傾向スコアリングでは、そうした質問に回答し、行動を起こす気持ちのある訪問者を特定することができます（後で、設定し、スコアを割り当てることができます）。

In addition, you can use filters to define a subset of visitors to be scored using the optional **[!UICONTROL Training Filter]** feature. フィルターを適用しない場合は、すべての訪問者がスコアリングのターゲットになります。

## 傾向スコアリングビジュアライゼーションの機能 {#section-28413bc7d33b42c59cecb427c1c5a3fa}

傾向スコアリングビジュアライゼーションを開くには、//// **[!UICONTROL Add]** をク **[!UICONTROL Visualization]** リッ **[!UICONTROL Predictive Analytics]** クして **[!UICONTROL Scoring]** くださ **[!UICONTROL Propensity Score]**&#x200B;い。

![](assets/propensity_visualization_GO.png)

傾向スコアリングビジュアライゼーションには次の機能があり、ツールバーからアクセスできます。

| ツールバーの機能 | 説明 |
|---|---|
| 移動 | パラメーターを設定した後にクリックすると、スコアリング処理が実行されます。 |
| リセット | ビジュアライゼーションのすべての設定をクリアします。 |
| ロード | 以前に作成した ScoreDim をロードして、スコアリングモデルを変更または再構築できるようにします。 |
| 保存 | 必要に応じてアクセスしたり開いたりできる Dim ファイルとして傾向スコアリングビジュアライゼーションを保存します。 |
| 送信 | サーバー側で処理するためにスコアリングタスクを送信します。 |
| オプション | トレーニングフィルターを設定して、訪問者のサブセットを制限します。The default filter is **[!UICONTROL Train on Everyone]**, but you can change it by making workspace selections or building a filter using the **[!UICONTROL Filter Editor]**. |
| ターゲットを設定 | 従属変数を設定します。 |
| 指標 | 指標を独立変数として追加します。 |
| エレメント | Drag Dimension elements using the `<Ctrl>` + `<Alt>` keys from Dimension tables. |

**関連項目**：

* Folio Builder[ゲインチャートとリフトチャート](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)。これらのビューは、完全なスコアリングモデルから、または [!DNL Add Visualization> Predictive Analytics > Scoring.]
* [モデルビューア](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd)。これらのビューは、完全なスコアリングモデルから、または [!DNL Add Visualization> Predictive Analytics > Scoring.]
* The [Complex Filter Description](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) feature.

## 傾向スコアリングビジュアライゼーションの使用 {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **スコアリング対象の訪問者の母集団を定義するフィルターを 1 つ以上定義します**。This optional **[!UICONTROL Training Filter]** lets you target visitors based on selected criteria. フィルターが適用されていない場合、すべての訪問者がスコアリング対象です。トレーニングフィルターが設定されている場合、各訪問者にはスコアが与えられますが、スコアリング結果は、定義した訪問者の母集団に対して意味を持ちます。
* **ポジティブな訪問者を特定します**。従属変数を定義するには、目的の結果に一致するポジティブな訪問者を特定するターゲットフィルターを指定します。これは、売上高 > $10 のように単純でも、もっと複雑なフィルターでも構いません。
* **ターゲットフィルターをトレーニングフィルターと同じにすることはできません**。必然的に、ターゲットフィルターはトレーニングフィルターに追加されるものである必要があるので、スコア対象の訪問者母集団のポジティブなサブセットを定義します。
* **傾向スコアリングアルゴリズムへの入力として、関心のある変数（独立変数）を選択します**。これには、指標や、ディメンションの個別のエレメントを選択できます。傾向スコアリングは、 [訪問者クラスタリング](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). システムは、以前設定したトレーニングフィルター（存在する場合）に一致する一定量のサンプルの取得を開始します。現在、サンプルサイズは、（トレーニングフィルターで定義した）スコアリング母集団の 10％、最小 20,000、最大 100,000 に設定され、スコアリング母集団のサイズに縛られます。

* スコアディメンションには、訪問者がターゲット変数に一致する確率を示す 0 ～ 100％の範囲のエレメントが含まれます。

