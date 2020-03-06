---
description: ワークシート式とセル参照の使用に関する概念的な情報です。
solution: Analytics
title: ワークシート式
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークシート式{#worksheet-expressions}

ワークシート式とセル参照の使用に関する概念的な情報です。

次のワークシートは、銀行の Web サイトのオンライン申請フォームに関するもので、提供される申請ウィザードのページを表示する訪問者の詳細を示しています。

![](assets/client-wkst.png)

* 列 A は、評価対象の訪問者のカテゴリーのリストです。「Visitors」は訪問者、「Referred Visitors」は参照による訪問者、「Referred Visitors from Ref A」はリファラー A からの訪問者を示しています。
* 列 B は、「Apply Now（今すぐ申請）」ページを表示した各カテゴリーの訪問者の数を示しています。
* 列 C は、「Apply Now」ページと「Application Wizard（申請ウィザード）」ページの両方を表示した訪問者を示しています。
* 列 D は、「Apply Now」を表示した 3 つのカテゴリー内の訪問者のうち、「Application Wizard」ページも表示した人の割合です。

このワークシートによると、「Apply Now」ページを表示した、リファラー A からの訪問者のうち約 55 ％が「Application Wizard」ページも表示したことがわかります。

次の表に、前の例のワークシートで使用したサンプル式を示します。

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ワークシートのセル </th> 
   <th colname="col2" class="entry"> 数式 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>「Apply Now」ページを表示した訪問者 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>「Apply Now」ページを表示した、参照による訪問者 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>「Apply Now」ページを表示した、リファラー A からの訪問者 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath">Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した訪問者 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した、参照による訪問者 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した、リファラー A からの訪問者 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath">Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した訪問者の割合 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した、参照による訪問者の割合 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>「Apply Now」ページと「Application Wizard」ページを表示した、リファラー A からの訪問者の割合 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

他のビジュアライゼーションと同様に、ワークスペース内の別のビジュアライゼーションで選択を行うと、ワークシートは自動的に更新されます。選択について詳しくは、「[ビジュアライゼーションに選択範囲を作成する](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)」を参照してください。

次の Web データの例では、日別のセッションのビジュアライゼーションで、一部の日付のセッションデータが選択されています。このワークシートによると、選択した期間では、「Apply Now」ページを表示した、リファラー A からの訪問者のうち約 69 ％が「Application Wizard」ページも表示したことがわかります。この選択をしない場合は（上の例で示したように）、リファラー A からの訪問者のうち約 55 ％が、「Apply Now」ページとともに「Application Wizard」ページを表示していました。

![](assets/client-exp.png)

## セル参照の使用 {#section-0004e315c9c94d359b1a8a39794ba555}

式の中の文字列は、それ自体であっても、ワークシート内の別の式の中でも、セル参照に置き換えられます。

* **単純なセル参照：**&#x200B;セル A2 にはテキスト Visitors があり、見出しとして使用されています。Cell B2 contains [!DNL eval(A1)], which evaluates to [!DNL =Visitors].

* **フィルターセル参照：**&#x200B;セル A5 には昨日の日付が含まれています。Cell B5 contains [!DNL Visitors[ Day=A5 ]], which evaluates to the number of Visitors yesterday.

* **連結セル参照：**&#x200B;セル A5 には今日の日付が含まれ、セル A6 には 08:00 ～ 08:59 の 1 時間の期間が含まれます。Cell B6 contains [!DNL Visitors[ Hour=A5+” ”+A6 ]], which evaluates to the number of Visitors today between 8:00 AM and 9:00 AM.

