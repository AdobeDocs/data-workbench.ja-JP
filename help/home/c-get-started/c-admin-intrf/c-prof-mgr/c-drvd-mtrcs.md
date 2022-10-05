---
description: 指標エディターを使用して、新しい指標（派生指標）を定義したり、既存の指標定義を編集したりできます。
title: 派生指標の使用
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 36%

---

# 派生指標の使用{#work-with-derived-metrics}

{{eol}}

指標エディターを使用して、新しい指標（派生指標）を定義したり、既存の指標定義を編集したりできます。

指標に関する詳細は、この節および [クエリ言語構文](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)を参照し、 *指標、Dimension、フィルターガイド*.

## 派生指標の作成 {#section-d57b98bf0a9940daba4920ff7efc808d}

次を使用する： [!DNL Metric Editor] ：名前、数式および形式で新しい指標を定義します。この指標は、後で使用するために User\*profile_name*\Metrics フォルダーに保存されます。

1. 新しい [!DNL Metric Editor] の使用 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** メニューオプションを使用するか、右クリック **[!UICONTROL User]** 」列をクリックし、指標を作成するフォルダーの列と **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   A [!DNL Metric Editor] が表示されます。

1. 名前パラメーターに、新しい指標の名前を入力します。

   スペース（ ）は使用できますが、アンダースコア（_）は使用できません。また、以下の記号は使用できません。

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. 数式パラメーターに、新しい指標の式を入力します。フィルターは角括弧内で定義する必要があります [ ] を式に含めます。

   その他の指標式の構文ルールについては、 [指標式の構文](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

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

1. 右クリック **[!UICONTROL (New)]** をクリックし、 **[!UICONTROL Save]**.

   Data Workbenchを保存すると、新しい指標を表すファイルがコンピューターの Metrics Installation ディレクトリ（\User\*profile name*\Metrics フォルダー）に作成されます。

   ![](assets/vis_MetricEditor_NewAndEditing.png)

これで、組み込み指標と同様に選択して、現在のプロファイルで新しい指標を使用できます。指標メニューに指標が表示される順序を変更するには、「[order.txt ファイルを使用したメニューのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)」を参照してください。

作成した指標をプロファイルのすべてのユーザーが使用できるようにするには、 [!DNL Profile Manager]. 詳しくは、 [作業プロファイルへのファイルの公開](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## 派生指標の編集 {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. 内 [!DNL Profile Manager] または [!DNL Metrics Manager]、 *プロファイル名* 列で、編集する指標ファイルのチェックマークを右クリックし、 **[!UICONTROL Make Local]**.
1. 指標ファイル ( [!DNL User] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >また、 [!DNL Metric Editor] ビジュアライゼーション内の指標関連の領域を右クリックして指標メニューを表示します。 詳しくは、 [指標メニューとDimensionメニューの操作](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. 内 [!DNL Metric Editor]、必要に応じて、 [新しい派生指標の作成](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   編集した指標をプロファイルのすべてのユーザーが使用できるようにするには、 [!DNL Profile Manager]. 詳しくは、 [作業プロファイルへのファイルの公開](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
