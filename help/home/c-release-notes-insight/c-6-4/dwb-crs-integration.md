---
description: 顧客レコードサービス（CRS）のエクスポート機能を使用して、Data Workbench のデータを Adobe Analytics コアサービスにエクスポートし、Analytics のその他の機能（Reports & Analytics など）と統合できます。
title: Analytics コアサービスへのエクスポート
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Analytics コアサービスへのエクスポート{#exporting-to-analytics-core-services}

顧客レコードサービス（CRS）のエクスポート機能を使用して、Data Workbench のデータを Adobe Analytics コアサービスにエクスポートし、Analytics のその他の機能（Reports &amp; Analytics など）と統合できます。

>[!NOTE]
>
>CRSのエクスポート機能を動作させるには、訪問者のAnalytics IDがExperience Cloud IDサービス(ECID)に基づいている必要があります。 訪問者のECIDはData Workbenchで設定できますが、クライアントが猶予期間中の場合、または訪問者のcookieがECIDに置き換えられていない場合、CRSエクスポートはその訪問者に対しては機能しません。 詳しくは、「訪問者の識別 [と](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html) IDサービスの猶予 [期間」を参照してください](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html)。

From a **Detail Table** (right-click **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]** in a workspace), you can set attribute values and the variables required to integrate with Analytics&#39; Reports &amp; Analytics (using Adobe Pipeline Services).

1. **テーブルのヘッダーを右クリックして、「新しい顧客レコードサービスのエクスポート」をクリックします。**

   ![](assets/6_4_CRS.png)

1. **エクスポートファイルに名前を付けて、保存します。**

   エクスポートファイルの編集ウィンドウが開きます。

1. ******Query／CRS Configuration**&#x200B;を開きます。
1. **CRS Attributes を右クリックして、「新規追加」を選択します。**
1. **CRS Attributes*****のパラメーター*****を入力します**。

   新しいエントリを開き、エクスポートファイルの「*CRS Attributes*」セクションの値を入力または確認します。

   ![](assets/6_4_CRS1.png)

   <table id="table_8156A2C66C0E41D381C31F1082CCA479"> 
    <tbody> 
      <tr> 
      <td colname="col1"> <p><b>Attribute Name</b> </p> </td> 
      <td colname="col2"><i>Reports &amp; Analytics</i> に表示される <i>Customer Attributes</i> 変数の名前。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"><b>Attribute Type</b> </td> 
      <td colname="col2"> <p>このパラメーターは、（<i>int</i>、<i>string</i>）の値を受け入れます。 </p> <p>注意：属性が Analytics に<b>登録されていない</b>場合： <p> 
      <ul id="ul_B77BF6FDA3FB4F1BBF9380C2FD938270"> 
       <li id="li_3D099456AF6B4103B227D841C81AB936">属性は、Analytics がサポートしている任意の有効な属性タイプで作成されます（このリリースでは <i>string</i> と <i>int</i> に限定されています）。 </li> 
       <li id="li_EA1DBDB2E6BE49278C6CD6A5503EDC8A">無効な属性タイプが入力された場合は、Analytics への登録に失敗したというエラーが表示されます。 </li> 
      </ul> </p> <p>属性が Analytics に<b>既に登録されている</b>場合： </p> <p> 
      <ul id="ul_16415B639F1C49A5AE9932C128184171"> 
       <li id="li_83C90D44FE5C4D979DEA786660C7F3EC">既に登録されている属性に対して正しい属性タイプを入力してください。 </li> 
       <li id="li_02C5024E335C4C59B4F7B0084232CC24">属性に対して誤ったタイプを入力した場合の動作は、Analytics による属性タイプの処理によって異なります。 </li> 
      </ul> </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p><b>Field Name</b> </p> </td> 
      <td colname="col2">属性値の選択元となるディメンションまたは指標の名前。 <p>注意：<i><b>CRS Attributes</b></i> の下の <i>Field Name</i> は、<b>Output<i> Fields</i>／<i>Field Name</i></b>（選択した属性に基づいて自動的に設定される）と同じにする必要があります。<i>Field Name</i> が無効な場合は、エクスポートが実行されません。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Right-click **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**.
1. Enter the **[!UICONTROL Report Suite ID]**.

   新しいエントリを開き、エクスポートファイルの「*Report Suite*」セクションの値を入力または確認します。

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>レポートスイート</b> </td> 
      <td colname="col2">ID of the report suite in <i>Reports &amp; Analytics</i> identifying the <i>Customer Attribute</i> variables being exported. <p> <p>注意：<i>Reports &amp; Analytics</i> を使用して複数のレポートスイートを追加することができますが、Data Workbench 6.4 は index 0<i></i> で識別される単一のレポートスイートのみをエクスポートします。 <p>このフィールドに入力されるレポートスイートの値は、レポートスイートIDです（レポートスイートの名前ではありません）。 </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. ECID Fieldパラメーターを入力します。

   **ECIDフィールド**:Adobe Experience Cloud IDを表す、プロファイル内のディメンションの名前。 これは必須フィールドで、入力した無効な分析コード値はエクスポートされません。

1. （オプション）Visitor ID Fieldパラメーターに入力します。

   **訪問者IDフィールド**:ユーザーがデータ内の訪問者に対して他のカスタムIDを送信する場合は、カスタム訪問者IDを表すディメンションの名前をここに入力します。 これはオプションのフィールドで、空のままにすることができます。
