---
description: 傾向スコアリングビジュアライゼーションを使用するには、この手順に従います。
title: 傾向スコアリングの設定
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 63%

---

# 傾向スコアリングの設定{#setting-up-propensity-scoring}

{{eol}}

傾向スコアリングビジュアライゼーションを使用するには、次の手順を実行します。

1. 新しいワークスペースを開き、 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. を **[!UICONTROL Target]** （依存変数）。

   従属変数を設定するには、次を選択します。

* **Dimension要素**:ワークスペース内で右クリックし、「 」を選択します。 **[!UICONTROL Table]**. 次に、従属変数としてディメンションエレメントを選択します。

   OR

* **[!UICONTROL Filter Editor]**&#x200B;に移動します。クリック **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** をクリックして、フィルターエディターのビジュアライゼーションを開きます。

   ![](assets/propensity_visualization_filter_editor.png)

   依存変数としてDimension要素またはフィルターを選択した後、 **[!UICONTROL Set Target]**」に、依存変数を説明する名前を入力します。 「**[!UICONTROL OK]**」をクリックして（フィルターボックスが強調表示されていることを確認し）ターゲットを設定します。

   ![](assets/propensity_visualization_setTarget.png)

   ターゲットに付けた名前が左側のペインに表示される従属変数の名前になります。
1. 独立変数を追加します。

   指標またはディメンションエレメントを使用して独立変数を追加します。

   ![](assets/propensity_visualization_metrics.png)

* **指標**. 傾向スコアリングツールバーで、 **[!UICONTROL Metrics]** メニュー

* **Dimension要素**:ワークスペース内で右クリックし、「 」を選択します。 **[!UICONTROL Table]**. 1 つ以上のDimension要素を選択し、左の列（の下）にドラッグします。 **[!UICONTROL Independent Variables]** または **[!UICONTROL Element]** を使用して `<Ctrl>` + `<Alt>` キー。

1. 設定 **[!UICONTROL Training Filter]**. スコアを付ける訪問者のセットを定義するには、 **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** を設定します。 これにより、スコア対象の訪問者のみを使用してデータのサブセットが作成されます。例えば、先月訪問した訪問者、オーストラリア在住の訪問者または特定の製品を見た訪問者を使用できます。

   デフォルトのフィルターは **[!UICONTROL Train on Everyone]**&#x200B;を有効にすると、 **[!UICONTROL Dimension Elements]** を使用して、テーブル内またはフィルターを作成する **[!UICONTROL Filter Editor]**.

   ディメンションエレメントを選択するか、フィルターを作成し、アクティブ化したら、**オプション**／**トレーニングフィルターを設定**&#x200B;をクリックし、フィルターを説明する名前を入力し、「**[!UICONTROL OK]**」をクリックします。
1. すべての入力を特定したら、 **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   スコアリング処理が開始され、データが複数回渡されます。その後、割合を示す線の上に結果が棒グラフとして表示されます。
1. 傾向スコアを保存します。

   6.1 以降では、傾向スコアの保存を使用する際にオプションが表示されるようになりました。

* ディメンション
* ディメンションと指標

   2 つのファイル（ディメンションと定義された指標の両方）を保存できます。

   >[!NOTE]
   >
   >傾向スコアを処理のために送信する場合、ディメンションのみが得られます。

   派生指標は、関連する平均スコア指標です。
1. 正解率を確認します。

   システムが表示されます **[!UICONTROL Model Complete]** プロセスが完了したら、スコアリングモデルを生成します。

   右クリック **[!UICONTROL Model Complete]** は、システムで定義されたスコアリングモデルの精度を識別します。 0% ～ 100%の値で、訪問者が **[!UICONTROL Target]** 変数を使用します。

   混同行列は、実際のポジティブ（AP）、実際のネガティブ（AN）、予測されたポジティブ （PP）、予測されたネガティブ（PN）の組み合わせによる 4 カウントを付与します。これらの数値は、真の正解とわかっている 20 ％を差し引いた検定データに、結果のスコアリングモデルを適用することで取得されます。スコアが 50％を超える場合、（定義されたイベントに一致する）ポジティブケースとして予測されます。

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b>正解率</b> </td> 
   <td colname="col2"> すべての予測から正しい予測を識別することで、モデルの正確さを示します。 <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>再現率</b> </td> 
   <td colname="col2"> スコアリングモデルを再度特定する能力を示します。 <p><b>TP / (TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>精度</b> </td> 
   <td colname="col2">矛盾のレベルを示します。 <p>TP / (TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. を開きます。 [リフトチャートまたはゲインチャート](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)、または [モデルビューア](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   を右クリックします。 **モデル完了** ビジュアライゼーションと選択 **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]**&#x200B;または **[!UICONTROL Model Viewer.]**
