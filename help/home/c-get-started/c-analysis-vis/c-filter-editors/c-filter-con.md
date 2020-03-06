---
description: 新しいフィルターの作成や、新しいフィルターへの条件の追加など、フィルター条件の操作に関する情報です。
solution: Analytics
title: フィルター条件の操作
topic: Data workbench
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Working with filter conditions{#working-with-filter-conditions}

新しいフィルターの作成や、新しいフィルターへの条件の追加など、フィルター条件の操作に関する情報です。

## Create a filter {#section-70ba51ae625e493fa3ca70b93ffba406}

* 右クリックして、/を選択し、ワークスペースでフィルターエディタ **[!UICONTROL Add Visualization]** ーを開きま **[!UICONTROL Filter Editor]**&#x200B;す。

   - または -

* If you already have a filter editor open and a filter loaded, right-click the current filter’s name and click **[!UICONTROL New Blank Filter]**.

## Add a condition to a new filter {#section-50986db80f1148c489630a8a63fe9f28}

1. 新しいフィルターを作成します。（「フィルターを適用」ではなく）「フィルターを作成」がハイライトされていて、フィルターを作成モードで作業していることを確認します。
1. マークされた領域内で右クリックし、次 **[!UICONTROL Right-click to build filter]** のいずれかのオプションを選択します。

   * インクルージョンフィルターを作成するには、をクリックしま **[!UICONTROL Include group with]**&#x200B;す。
   * 除外フィルターを作成するには、をクリックしま **[!UICONTROL Exclude group with]**&#x200B;す。

1. フィルターを追加する条件のタイプを選択します。

   以下の表に、使用可能なフィルター条件のタイプについて説明します。

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 条件のタイプ </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ワークスペース選択 </p> </td> 
   <td colname="col2"> <p>ワークスペース内の選択範囲に基づいてフィルター条件を定義します。このオプションは、ワークスペース内に 1 つ以上の選択範囲が存在する場合にのみ使用可能です。 </p> <p>選択範囲に関する詳細情報を表示するには、条件を右クリックして、「<span class="uicontrol">詳細を表示</span>」をクリックします。条件の引き出し線が表示されます。 </p> <p>ワークスペース内に別の選択範囲を作成した場合、その選択範囲を最初の選択範囲の 2 次条件として追加できます。選択範囲は、論理 AND としてグループ化されます。したがって、条件によって含める、または除外するデータは、すべてのワークスペース選択を満たす必要があります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 つ以上 </p> </td> 
   <td colname="col2">選択したディメンションの 1 つ以上の（任意の）要素の存在に基づいてフィルター条件を定義します。この条件を編集するには、条件を右クリックし、「<span class="uicontrol">条件を次に変更：</span>」をクリックします。使用可能なディメンションのいずれかをクリックします。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数式 </p> </td> 
   <td colname="col2"> <p>入力した数式に基づいてフィルター条件を定義します。フィルターを機能させるには、適切な構文を使用する必要があります。 </p> <p> <p>注意：フィルターを定義するための構文について詳しくは、「フィルター式の構 <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> 文」を参照してくださ</a>い。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指標の値 </p> </td> 
   <td colname="col2"> <p>指定した指標の値に基づいてフィルター条件を定義します。 </p> <p>条件を定義するには、以下の手順を実行します。 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA"><span class="uicontrol">[レベルを選択]</span>／<span class="uicontrol">レベルを変更</span>を右クリックして、データセット内のディメンションのリストからレベルと指標を選択します。 </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F"><span class="uicontrol">[指標を選択]</span>／<span class="uicontrol">指標を変更</span>を右クリックして、データセット内の指標のリストから指標を選択します。 </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">「次の値より小さい」を右クリックし、「<span class="uicontrol">比較を変更</span>」をクリックして、使用可能な比較条件（次の値より小さい、次の値より大きい、固定値、最小で、最大で）のいずれかを選択します。 </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">指標に対して目的の値を入力します。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最初 / 最後 </p> </td> 
   <td colname="col2"> <p>指定したディメンションに関して、あるレベルを含める、または除外することができるフィルターを定義します。例えば、最初 / 最後フィルターを指定して、以下を含める（または除外する）ことができます。 </p> <p>最後のページビューが <span class="filepath">/hme/rts/Our Rates</span> のページだったセッション </p> <p>最初 / 最後条件を定義するには、次のようにします。 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">フィルターエディターで、新しい条件として、<span class="uicontrol">グループを含める</span>または<span class="uicontrol">グループを除外</span>／<span class="uicontrol">最初 / 最後</span>を選択します。 </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC"><span class="uicontrol">[コンテナを選択]</span>／<span class="uicontrol">コンテナを変更</span>を右クリックして、コンテナを選択します。 </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">「<span class="uicontrol">最初</span>」または「<span class="uicontrol">最後</span>」を右クリックして、レベルを指定します。 </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">右クリックしてディメンションを指定し、使用可能なフィールドに値を入力します。 </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">「<span class="uicontrol">適用</span>」をクリックします。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The filter in this example defines a first/last filter for users whose last page view was [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. （オプション）フィルターにさらに条件を追加するには、フィルターを作成しているウィンドウの領域内で右クリックし、フィルターのタイプを選択し（手順 2 を参照）、条件ルールを選択します（手順 3 を参照）。

   >[!NOTE]
   >
   >複数の包含条件は、論理ORとしてグループ化されます。 したがって、フィルターによって含めるデータは、定義された包含条件の少なくとも 1 つを満たしている必要があります。複数の除外条件も論理 OR としてグループ化されます。除外するデータは、除外条件の少なくとも 1 つを満たしている必要があります。

次の例のフィルターは、多数の映画を評価したが、どの映画にも高いスコア（4 または 5）を与えなかった映画視聴者（ユーザー）で構成されるデータのサブセットを定義します。このフィルター（Very Hard to Please）は、次の 2 つの条件で構成されています。

* **指標の値条件：**&#x200B;この条件は、500 以上の映画を評価したユーザーを含めます。
* **ワークスペース選択条件：**&#x200B;この条件は、いずれかの映画に 4 または 5 のスコアを与えたユーザーを除外します。Score ディメンションから選択された要素が 4 または 5 であったことを引き出し線が示しています。

![](assets/vis_FilterEditor_ExampleMovies.png)

## Delete a filter condition {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>条件を削除できるのは、フィルターを設計モードで作業している場合のみです。 ワークスペースにフィルターを適用していた場合、そのフィルターの 1 つ以上の条件を削除するには、「フィルターを作成」をクリックしてフィルターを作成モードに戻る必要があります。

* 条件の左側の **x** をクリックして、条件を削除します。

## 条件の説明の編集 {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

フィルターに追加した各条件に説明を追加できます。必要に応じて、説明を編集または削除できます。

>[!NOTE]
>
>条件の説明は、フィルターを設計モードで作業している場合にのみ表示されます。

* 条件を右クリックし、をクリックしま **[!UICONTROL Edit description]**&#x200B;す。

   * To add or edit a description, type the description in the [!DNL Edit condition description] field. フィルターエディターウィンドウの条件の上に、説明が引用符で囲まれて表示されます。

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* 説明を削除するには、をクリックしま **[!UICONTROL Remove description]**&#x200B;す。 条件はフィルターエディターウィンドウ内に表示されたままです。

