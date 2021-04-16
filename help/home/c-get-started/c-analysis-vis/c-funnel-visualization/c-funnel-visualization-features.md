---
description: ファンネルビジュアライゼーションには、複数のディメンション、生の訪問者数、各手順における訪問者の割合および個別のスコープを使用してファンネルを構築できる機能が用意されています。
title: ファネル機能
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 83%

---

# ファネル機能{#funnel-features}

ファンネルビジュアライゼーションには、複数のディメンション、生の訪問者数、各手順における訪問者の割合および個別のスコープを使用してファンネルを構築できる機能が用意されています。

ここでは、ファンネルビジュアライゼーションの基本的な機能を紹介します。

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> 最初のエレメント </td> 
   <td colname="col2"> プロセスの最初のファンネル手順。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> 3 番目のエレメント </td> 
   <td colname="col2">プロセスの 3 番目のファンネル手順。 <p><p>注意：同じディメンションから要素を選択しないでください。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> フォールスルー率 </td> 
   <td colname="col2"> 3 つのスコープで表示されている定義済みのパスを完了した割合。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> フォールアウトブラウザー </td> 
   <td colname="col2">フォールアウトの矢印。右クリックして「<span class="uicontrol">パスブラウザーを追加</span>」をクリックすると、訪問者が通った他のパスが表示されます。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> フォールアウト率 </td> 
   <td colname="col2">パスを完了しなかったユーザーの 3 つのスコープのフォールアウトを示す割合。 <p>3 つのスコープの割合が表示されます。 </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" />  前のステップからこのステップまでのフォールアウトの割合。 </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" />  ファンネルの最初の手順からのフォールアウトの割合。 </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" />  訪問者の総数に基づくフォールアウトの割合。 </p></td> 
  </tr> 
 </tbody> 
</table>

## ファンネルの手順 {#section-96a6732558dd4740b73541844f06d3ef}

ファンネル内のディスクはナビゲーションの手順を表し、コーンはある手順から次の手順までのフォールスルーを表し、矢印はフォールアウトを表します。コーンをクリックすると、その時点でフォールスルーしたユーザーが選択され、現在のワークスペースフィルターに含まれます。矢印をクリックすると、フォールアウトした訪問者が選択されます。

>[!NOTE]
>
>ファンネルビジュアライゼーションには、適用できる手順は8個までに制限されています。

## ファンネルのその他の機能 {#section-22a3582db8114ca8bce77f50bbbf296a}

* **ファンネルのクリップとレベルを調整します**。ビジュアライゼーションメニューから「ファンネル」オプションを選択します。ファンネルが作成されたら、タイトルを右クリックして、システム内の任意の可算指標に合わせてクリップとレベルを調整できます。

   ![](assets/funnel_path_browser_9.png)

* **複数のエレメントをドラッグします**。&lt;a0/追加> + `<Alt>`キーを押しながら、Dimensionテーブルからファネルに要素をドラッグ&amp;ドロップして、ファネルに追加します。 `<Ctrl>`複数のDimensionを選択し（`<Ctrl>`キーを押しながらクリック）、`<Ctrl>` + `<Alt>`キーを使用してファネルのビジュアライゼーションにドラッグすることで、項目テーブルから複数の手順を同時にドラッグできます。
* **ステップを削除**：ビジュアライゼーション内のステップを右クリックし、「**はい**」をクリックして、要素を削除します。

   ![](assets/funnel_path_browser_4.png)

* **ファンネルにドラッグした手順を並べ替えます**。手順を並べ替えるには、単純に手順をクリックして選択し、別の位置にドラッグします。
* **パスブラウザーを開きます**。顧客がプロセスをフォールスルーまたはフォールアウトした手順の詳細を確認するには、[パスブラウザーの追加](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119)機能を使用します。

* **複数の手順を追加します**。各ファンネルビジュアライゼーションには、最大で 8 個の手順を追加できます。
* **指標を変更します**。各手順での訪問回数などの指標をカウントするために、指標を変更できます。利用可能なオプションは、データセットによって異なります。
* **表形式ビューで表示します**。タイトルを右クリックしてファネルのビジュアライゼーションメニューを表示し、**[!UICONTROL Show Tabular View]**&#x200B;をクリックします。 表形式の表示にしたら、**[!UICONTROL Show Graph View]**&#x200B;を選択して、ファネルのグラフィック表現に戻ることができます。 表形式ビューを開くには、タイトルを右クリックし、メニューから「表形式ビューを表示」を選択します。

* **配列を比較します**。2 つの類似したシーケンスを比較する効率的な方法は、2 つのビジュアライゼーションを並べて表示することです。複製機能を使用すると、表形式ビューとグラフビューの両方を並べて表示できます。開くには、タイトルを右クリックし、メニューから「複製」を選択します。
