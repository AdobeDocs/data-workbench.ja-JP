---
description: 指標エディターを使用して、新しい指標（派生指標）を定義したり、既存の指標定義を編集したりできます。
solution: Analytics
title: 派生指標の操作
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 派生指標の操作{#work-with-derived-metrics}

指標エディターを使用して、新しい指標（派生指標）を定義したり、既存の指標定義を編集したりできます。

この節およびクエリ言語構文で提供される指標の詳細については、『指標 [、ディメンション、フィル](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)ターガイド』を参照してください **。

## Create a derived metric {#section-d57b98bf0a9940daba4920ff7efc808d}

You use a [!DNL Metric Editor] to define a new metric by name, formula, and format, which is saved to the User\*profile_name*\Metrics folder for later use.

1. Open a new [!DNL Metric Editor] using the **[!UICONTROL Admin]** > **[!UICONTROL Profile]** menu option or by right-clicking the **[!UICONTROL User]** column for the folder in which you want to create the metric and clicking **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   が表示さ [!DNL Metric Editor] れます。

1. 名前パラメーターに、新しい指標の名前を入力します。

   スペース（ ）は使用できますが、アンダースコア（_）は使用できません。また、以下の記号は使用できません。

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 数式パラメーターに、新しい指標の式を入力します。フィルターは角括弧で囲んで定義する必要があります [ ] を式の中で使用します。

   追加の指標式の構文ルールについては、「指標式の構 [文」を参照してください](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)。

   以下の表に、拡張指標の式の例を示します。

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 拡張指標名 </th> 
      <th colname="col2" class="entry"> 式 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Percent First Sessions（開始セッションの割合） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sessions [Session_Number="1"]/Sessions</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Conversion First Sessions（開始セッションのコンバージョン） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversion [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Average Value Per Visitor（訪問者あたりの平均値） </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Value/Visitors</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >適切な式を入力すると、プレビュー行に新しい指標の値が表示されます。 式にエラーがある場合は、プレビュー行にエラーメッセージが表示されます。

1. 右クリックし、を **[!UICONTROL (New)]** クリックしま **[!UICONTROL Save]**&#x200B;す。

   指標を保存すると、新しい指標を表すファイルがData Workbenchのインストールディレクトリ\User\*profile name*\Metricsフォルダー内のコンピューターに作成されます。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

これで、組み込み指標と同様に選択して、現在のプロファイルで新しい指標を使用できます。指標メニューに指標が表示される順序を変更するには、「[order.txt ファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)」を参照してください。

If you would like all users of the profile to use the metric that you created, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Edit a derived metrics {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. In the [!DNL Profile Manager] or [!DNL Metrics Manager], in the *profile name* column, right-click the check mark for the metric file that you want to edit, then click **[!UICONTROL Make Local]**.
1. Right-click the check mark for the metric file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >You also can open a [!DNL Metric Editor] by right-clicking any metric-related area within a visualization to display the metric menu. 詳しくは、指標メニューとディメンシ [ョンメニューの操作を参照してください](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)。

1. In the [!DNL Metric Editor], edit and save the metric definition as necessary using Steps 2-4 in [Creating New Derived Metrics](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   If you would like all users of the profile to use the metric that you edited, you must publish it to the working profile using the [!DNL Profile Manager]. See [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

