---
description: ポジティブケースを指定し、データを評価する指標とディメンション入力を追加して、デシジョンツリーを設定し、デシジョンツリーを調べます。
title: デシジョンツリーの構築
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# デシジョンツリーの構築{#building-a-decision-tree}

ポジティブケースを指定し、データを評価する指標とディメンション入力を追加して、デシジョンツリーを設定し、デシジョンツリーを調べます。

デシジョンツリーを構築するには、次の手順に従います。

1. 新しいワークスペースを開きます。

   新しいワークスペースを開いたら、**追加**／**一時的にロック解除**&#x200B;をクリックする必要がある場合があります。

1. To open the Decision Tree Builder, right-click **[!UICONTROL Visualization]** > **Predictive Analytics** > **Classification** > **Decision Tree Builder**.

1. **ポジティブケース**&#x200B;を設定します。

   デシジョンツリーのポジティブケースを定義するには、ファインダーでディメンションを、またはテーブルでディメンションエレメントを選択するか、「フィルターを作成」でフィルターを作成します。実際には、ポジティブケースは、フィルター、ディメンション、エレメント、Data Workbench のすべてのタイプのビジュアライゼーション値など、ワークスペース内の複数の選択を組み合わせて定義できます。

   * ポジティブケースとして&#x200B;**フィルターを作成し、適用**&#x200B;します。Right-click in the workspace and select **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** to design and apply a filter.

   * ポジティブケースとして&#x200B;**ディメンション**&#x200B;を追加します。In the workspace, right-click and select **Tools** > **Finders** (or select **[!UICONTROL Add]** > **[!UICONTROL Finders]** in the left pane). 「**検索**」フィールドにディメンション名を入力し、ディメンションを選択します。

   * ポジティブケースとして&#x200B;**指標**&#x200B;を追加します。右クリックし、ツール/ファインダ **ー** ( **Tools** / **[!UICONTROL Add]** Finders **[!UICONTROL Finders]** )を選択するか、左ペインで/を選択して、指標テーブルを開きます。 ポジティブケースとして指標を選択します。

   * ポジティブケースとして&#x200B;**ディメンションエレメント**&#x200B;を追加します。Right-click in the workspace and select **[!UICONTROL Table]** to open dimension elements, then select from the dimension elements to set your positive case.

1. クリック **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   ここではポジティブケースが設定され、名前を付けることができます。The name will appear under the **[!UICONTROL Positive Case]** heading in the workspace.

   >[!NOTE]
   >
   >ポジティブケースを設定すると、デシジョンツリーでは現在のワークスペース選択が使用されます。これは、訪問者（または最上位レベルの可算が定義されているが、ほとんどの場合は訪問者）として定義できます。 これらは、（複数のポジティブケースではなく）単一のポジティブケースの単一のフィルターとして組み合わせられます。

   Clicking **[!UICONTROL Set Positive Case]** when there is no selection will clear the positive case.

1. (optional) Select **[!UICONTROL Set Population Filters]** to define the visitor population to be classified.

   母集団フィルターが適用されない場合、トレーニングセットはすべての訪問者から取得されます（デフォルトは「全員」です）。

   >[!NOTE]
   >
   >Click the **[!UICONTROL Show Complex Filter Description]** to view the filtering scripts for the Positive Case and Population Filter.

1. 入力として&#x200B;**指標**、**ディメンション**&#x200B;および&#x200B;**ディメンションエレメント**&#x200B;を追加します。

   入力を選択するには、ファインダーパネルから、または個々のディメンションエレメントのテーブルからドラッグ＆ドロップします。You can also select from the **[!UICONTROL Metrics]** menu in the toolbar.

   * 入力として&#x200B;**指標**&#x200B;を追加します。

      ツールバーから「指標」を選択します。**Ctrl** + **Alt** キーを押しながら、1 つまたは複数の指標をデシジョンツリービルダーにドラッグします。

      指標は、一意に色分けされた入力として&#x200B;**入力（指標）リスト**&#x200B;に表示されます。

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * 入力として&#x200B;**ディメンション**&#x200B;を追加します。

      ワークスペース内で右クリックし、**ツール**／**ファインダー**&#x200B;を選択して、ディメンション名を「**検索**」フィールドに入力します。 **Ctrl** + **Alt** キーを押しながら、ディメンションを選択して、ディメンションをデシジョンツリービルダーにドラッグします。

      ディメンションは、一意に色分けされ、**入力（ディメンション）リスト**&#x200B;に表示されます。

   * 入力として&#x200B;**ディメンションエレメント**&#x200B;を追加します。

      ワークスペースで、右クリックして、ディメンションテーブルを選択します。ディメンションエレメントを選択し、**Ctrl** + **Alt** キーを押しながら、選択したエレメントをデシジョンツリービルダーにドラッグします。

      ディメンションエレメントは、一意に色分けされ、**入力（要素）**&#x200B;リストに表示されます。
   >[!IMPORTANT]
   >
   >評価対象の入力は最大14個まで選択できます。 追加した入力が多すぎると、エラーメッセージが表示されます。

1. Select **[!UICONTROL Go]** from the toolbar.

   選択したディメンションと指標に基づいてデシジョンツリーが構築されます。買い物かごへの追加などの単純な指標の場合はすぐに作成されますが、複数のデータポイントを持つ滞在時間などの複雑なディメンションの場合は作成に時間がかかり、変換中に完了の割合が表示されます。その後、ツリーマップがプルーニングされ、ユーザーが操作できるように開きます。ディメンションと指標の入力は、ノード名に合わせて色分けされます。

   ![](assets/decision_tree_builder.png)

   ツリーがプルーニングされている場合、およびプルーニングされた分岐の後に予測が **true** か **false** が表示されている場合、リーフノードは緑色（true）または赤色（false）で表示されます。

   >[!NOTE]
   >
   >トレーニングサンプルは、ツリービルダーで使用するデータセットから取り出されます。 Data Workbench では、サンプルの 80％を使用してツリーを構築し、残りの 20％を使用してツリーモデルの正解率を評価します。

1. を使用して精度を確認しま **[!UICONTROL Confusion Matrix]**&#x200B;す。

   Click **[!UICONTROL Options]** > **[!UICONTROL Confusion Matrix]** to view the Accuracy, Recall, Precision and F-Score values. 100％に近いほど、よいスコアです。

   混同行列は、次の値の組み合わせを使用して、モデルの正解率の 4 カウントを付与します。

   * 実際の陽性（AP）
   * 予測された陽性（PP）
   * 実際の陰性（AN）
   * 予測された陰性（PN）
   >[!TIP]
   >
   >これらの数値は、20%のテストデータの結果のスコアリングモデルを除外し、既に真の答えとして知られているものを適用することで得られます。 スコアが 50％を超える場合、（定義されたフィルターに一致する）ポジティブケースとして予測されます。このとき、正解率 = (TP + TN)/(TP + FP + TN + FN)、再現率 = TP / (TP + FN)、精度 = TP / (TP + FP) です。

1. **デシジョンツリーを調べます**。

   デシジョンツリーが生成されたら、予測のパスを確認し、定義された基準を満たすすべての訪問者を特定することができます。ツリーでは、位置と色分けに基づいて各分岐の入力分岐が識別されます。例えば、「参照ドメイン」ノードを選択すると、その分岐につながっているノードがツリーの左側に色分けされて表示されます。

   リーフノードを選択すると、デシジョンツリーの分岐（ルールセット）を選択できます。

   この例では、訪問期間が 1 未満で、キャンペーンが存在せず、ページビュー数が少なくとも 1 回はあり、電子メールのサインアップがなく、訪問回数が少なくとも 1 回はある場合、この基準を満たし、注文が行われる予測確率は **94.73**％です。

   ![](assets/decision_tree_explore.png)

   **デシジョンツリーの操作**：ツリーの複数のノードを選択する場合は、普通に **Ctrl** キーを押しながらクリックすると追加でき、**Shift** キーを押しながらクリックすると削除できます。

   **色分けされたノード**：ノードの色は、Data Workbench によって割り当てられた入力のディメンションと指標の色と一致しています。

   プルーニングされた分岐のリーフレベルにある明るい緑色と赤色のノードでは、ノードが true または false として予測されています。

   | ![](assets/decision_tree_node_true.png) 明るい緑色 | ノードが true で、すべての条件が満たされていることを示します。 |
   |---|---|
   | ![](assets/decision_tree_node_false.png) 明るい赤色 | ノードが false で、すべての条件が満たされていないことを示します。 |

1. **デシジョンツリーを保存します**。

   デシジョンツリーは、様々な形式で保存できます。

   ![](assets/decison_tree_save.png)

   * 予測マークアップ言語（**PMML**）：アプリケーションでデシジョンツリーモデルを記述および交換するために使用される XML ベースのファイル形式。
   * true または false、パーセンテージ、メンバーの数および入力値のシンプルな列と行を表示する&#x200B;**テキスト**。
   * **ディメンション**&#x200B;と、予測結果のエレメントに対応する分岐。

