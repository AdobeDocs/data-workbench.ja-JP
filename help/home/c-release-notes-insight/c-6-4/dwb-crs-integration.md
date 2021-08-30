---
description: 顧客レコードサービス（CRS）のエクスポート機能を使用して、Data Workbench のデータを Adobe Analytics コアサービスにエクスポートし、Analytics のその他の機能（Reports & Analytics など）と統合できます。
title: Analytics コアサービスへのエクスポート
uuid: 8fd7e8d8-989a-4ad6-bab5-61bfd37b0201
exl-id: 573085e8-2260-4872-be90-a84ad61145bb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 59%

---

# Analytics コアサービスへのエクスポート{#exporting-to-analytics-core-services}

顧客レコードサービス（CRS）のエクスポート機能を使用して、Data Workbench のデータを Adobe Analytics コアサービスにエクスポートし、Analytics のその他の機能（Reports &amp; Analytics など）と統合できます。

>[!NOTE]
>
>CRSのエクスポート機能を動作させるには、訪問者のAnalytics IDがExperience CloudIDサービス(ECID)に基づいている必要があります。 ECIDは訪問者に対してData Workbenchで設定できますが、クライアントが猶予期間に入っている場合、または訪問者のCookieがECIDに置き換えられていない場合、その訪問者に対してはCRSエクスポートは機能しません。 詳しくは、 [訪問者の識別](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-visid.html)および[IDサービスの猶予期間](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html)を参照してください。

**詳細テーブル**（ワークスペースで&#x200B;**[!UICONTROL Tools]** / **[!UICONTROL Detail Table]**&#x200B;を右クリック）から、(Adobeパイプラインサービスを使用して)AnalyticsのReports &amp; Analyticsとの統合に必要な属性値と変数を設定できます。

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
      <td colname="col1"> <p><b>フィールド名</b> </p> </td> 
      <td colname="col2">属性値の選択元となるディメンションまたは指標の名前。 <p>注意：<i><b>CRS Attributes</b></i> の下の <i>Field Name</i> は、<b>Output<i> Fields</i>／<i>Field Name</i></b>（選択した属性に基づいて自動的に設定される）と同じにする必要があります。<i>Field Name</i> が無効な場合は、エクスポートが実行されません。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. **[!UICONTROL Report Suite]** > **[!UICONTROL Add New]**&#x200B;を右クリックします。
1. **[!UICONTROL Report Suite ID]**&#x200B;と入力します。

   新しいエントリを開き、エクスポートファイルの「*Report Suite*」セクションの値を入力または確認します。

   <table id="table_A3279CADB74C441DA2E062E2123CE9D4"> 
    <tbody> 
      <tr> 
      <td colname="col1"><b>レポートスイート</b> </td> 
      <td colname="col2"><i>Reports &amp; Analytics</i>内のレポートスイートのID。エクスポートする<i>顧客属性</i>変数を識別します。 <p> <p>注意：<i>Reports &amp; Analytics</i> を使用して複数のレポートスイートを追加することができますが、Data Workbench 6.4 は index 0<i></i> で識別される単一のレポートスイートのみをエクスポートします。 <p>このフィールドに入力されるレポートスイートの値は、レポートスイートIDです（レポートスイートの名前ではありません）。 </p> </p> </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. ECID Fieldパラメーターを入力します。

   **ECIDフィールド**:Adobe Experience Cloud IDを表すプロファイル内のディメンションの名前。これは必須フィールドで、無効なディメンション値を入力してもエクスポートされません。

1. （オプション） Visitor ID Fieldパラメーターを設定します。

   **訪問者IDフィールド**:ユーザーがデータ内の訪問者に対して他のカスタムIDを送信する場合は、その訪問者がカスタム訪問者IDを表すディメンションの名前を入力します。これはオプションのフィールドで、空のままにすることができます。
