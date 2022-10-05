---
description: プレミアムメニューから最適なアトリビューションを開き、次の手順に従って、最適なアトリビューションモデルを作成します。
title: 最適なアトリビューションの作成
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
exl-id: e0a42374-2500-46a3-a72a-708ab2d228db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 58%

---

# 最適なアトリビューションの作成{#build-a-best-fit-attribution-model}

{{eol}}

プレミアムメニューから最適なアトリビューションを開き、次の手順に従って、最適なアトリビューションモデルを作成します。

の概要を見る [最適なアトリビューション](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. **最適なアトリビューション**&#x200B;を開きます。

   ワークスペースを開いて、 **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >最適なアトリビューションは、Adobe Analytics Premiumの機能で、プロファイルで Premium を有効にする必要があります。 それには、証明書を更新し、profile.cfg ファイルに Premium プロファイルを追加する必要があります。詳しくは、 [DWB サーバーのアップグレード：6.2～6.3](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-2-to-6-3-upgrade.md) （DWB 6.3 用）

1. を **[!UICONTROL Success]** 指標。

   >[!NOTE]
   >
   >指標は、 **[!UICONTROL Finder]** アトリビューションビジュアライゼーションの左側のウィンドウに表を追加するか、 **入力** メニュー

   クリック **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. 指標メニューが開きます。 ![](assets/attrib_set_success_metric.png)

   コンバージョンの成功を特定する指標を選択します。

1. （オプション）**売上高**&#x200B;指標を設定します。

   コンバージョンプロセス全体の売上高を評価する指標を設定します。

1. **タッチ**&#x200B;指標を設定します。

   >[!NOTE]
   >
   >タッチ指標の設定は、ディメンション要素をビジュアライゼーションにドラッグして成功指標を自動的に作成しようとする場合にのみ必要です。

   次をクリック： **[!UICONTROL Inputs]** メニューと選択 **タッチを設定**&#x200B;または Finder から指標をドラッグします。 ![](assets/attrib_set_touch.png)

   これは、ディメンションエレメントを入力として使用した場合に、チャネル指標を取得するために使用されます。

1. **成功**&#x200B;ウィンドウを設定します。

   「[!DNL Inputs > Success Window]」をクリックします。テーブルから日付範囲を選択し、成功ウィンドウに名前を付けます。クリック **[!UICONTROL Workspace Selection]** 選択した日付が、成功指標の時間範囲として割り当てられます。

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >成功ウィンドウはワークステーションの選択なので、成功ウィンドウに任意のディメンションを含めることができます。

1. を設定します。 **[!UICONTROL Touch Window]**.

   「[!DNL Inputs > Touch Window]」をクリックします。テーブルから日付範囲を選択し、タッチウィンドウに名前を付けます。クリック **[!UICONTROL Workspace Selection]** 選択した日付が、成功指標の時間範囲として割り当てられます。

   ![](assets/attrib_set_touch_window.png)

   デフォルトでは、 **タッチ** ウィンドウが **[!UICONTROL Success]** ウィンドウ

1. （オプション）トレーニングフィルターを設定します。

   また、ワークスペースで&#x200B;**トレーニングフィルター**&#x200B;を指定して、訪問者のデータをフィルターすることもできます。

   >[!NOTE]
   >
   >成功ウィンドウとタッチウィンドウの両方を設定して、現在のワークスペースの選択にトレーニングフィルターを適用し、データをさらに制限できます。

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >トレーニングセットは、常に、成功ウィンドウを満たす訪問者から作成されます。 フィルターエディターを使用してフィルターすると、成功ウィンドウで報告された訪問者のサブセットを作成することができます。

1. タッチを表すチャネル指標を指定します。

   指標をビジュアライゼーションにドラッグするか、 [!DNL Inputs] > [!DNL Add Channel] メニュー まだキャンペーンやチャネルに対して指標を定義していないが、チャネルを表すディメンションがある場合は、ビジュアライゼーションでタッチ指標の指定を使用して指標を自動的に作成することができます。

   例えば、タッチ指標がに設定されている場合、 [!DNL Hits]、および [!DNL dimension] 呼び出し [!DNL Media Type] を含む要素を使用 [!DNL Email], [!DNL Press Release], [!DNL Print Ad]、および [!DNL Social Media]を指定しない場合、ビジュアライゼーションはフォームのチャネル指標を生成します [!DNL Hits where Media Type = Email] 要素をビジュアライゼーションにドラッグ&amp;ドロップしたとき。

1. 「**移動**」を押します。

   最適な分析処理が実行され、選択した入力に基づいてチャネルごとにアトリビューションがグラフに表示されます。

   >[!NOTE]
   >
   >右クリック **モデル完了** アトリビューションモデルの統計を確認するには、完了した分析を参照してください。

   ![](assets/attrib_visualization.png)

完了すると、チャネルごとに計算されたアトリビューションモデルと、*売上高*&#x200B;指標の分布（設定されている場合）がグラフに表示されます。モデルは、内部的に保存することや、他のシステムにエクスポートすることができます。

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** および **[!UICONTROL Offline]** モードは、評価されるデータの待ち時間に基づいてアトリビューションモデルを作成する際に、異なる効果を生み出します。 ストリーミングモードでは、詳細 **[!UICONTROL Model Complete]** メッセージが表示されます。 オンラインモードとオフラインモードでは、詳細 **[!UICONTROL Local Model Complete]** が表示されます。

## オプションメニュー {#section-22288867f6c8483a8a38410f4b948346}

**オプション**&#x200B;メニューには、最適なアトリビューション分析を設定および表示するための高度な機能が用意されています。

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC">
 <thead>
  <tr>
   <th colname="col1" class="entry"> オプションメニュー </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"><span class="uicontrol">トレーニングフィルターを設定</span> </td>
   <td colname="col2"> トレーニングフィルターは、アトリビューションモデルを作成するときに、母集団をフィルターするために成功ウィンドウと組み合わせて使用します。これにより、分析する訪問者のみを含むデータのサブセットが提供されます。 <p>注意：経験豊富なユーザーは、フィルターを柔軟に活用して、成功ウィンドウとタッチウィンドウのタイムラインを超えて絞り込むことができます。例えば、時間範囲の選択に加えて、一連の<i>参照ドメイン</i>を選択して、それらのドメインからのユーザーのアトリビューションのみを調査できます。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol">複雑なフィルターの説明を表示</span> </td>
   <td colname="col2"> トレーニングフィルター、成功ウィンドウおよびタッチウィンドウのフィルターコードを表示します。 </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol">モデルを保存</span> </td>
   <td colname="col2"> 後で使用するために現在のアトリビューションモデルを保存します。 </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol">モデルの読み取り</span> </td>
   <td colname="col2"> 以前に保存したアトリビューションモデルを開きます。 </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol">プレゼンテーションの表示</span> </td>
   <td colname="col2"> プレゼンテーションのために上部のメニューバーを非表示にします。 </td>
  </tr>
  <tr>
   <td colname="col1"> <p><b>オプション／詳細</b>には、トレーニングセットサイズを設定し、クラスのバランスが悪い場合にどうするかを指定するための機能が含まれています。 </p> </td>
   <td colname="col2"> </td>
  </tr>
  <tr>
   <td colname="col1"><span class="uicontrol">詳細／トレーニングセットサイズ</span> </td>
   <td colname="col2"> <p>トレーニングセットサイズを設定します。 </p> <p>注意：デフォルトのトレーニングサイズは、大（250,000 人の訪問者用）です。 </p>
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD">
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">特小 = 50,000 </li>
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">小 = 75,000 </li>
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">標準 = 100,000 </li>
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">大 = 250,00 </li>
     <li id="li_34B60233C84F48F1BCB8040C5195411A">特大 = 500,000 </li>
    </ul> </td>
  </tr>
  <tr>
   <td colname="col1"><b>詳細／クラスのバランス</b> </td>
   <td colname="col2"> <p>データセットのサイズに基づき、クラスのアンバランスの問題に対して生成する入力レコードの数を特定および定義します。 </p> </td>
  </tr>
 </tbody>
</table>

| リセットと削除オプション | 説明 |
|---|---|
| **[!UICONTROL Reset Model]** | 次の **[!UICONTROL Reset]** メニュー、選択 **[!UICONTROL Reset Model]** をクリアし、入力指標を維持する。 |
| **[!UICONTROL Reset All]** | 次の **[!UICONTROL Reset]** メニュー、選択 **[!UICONTROL Reset All]** をクリックして、ビジュアライゼーションと入力指標をクリアします。 |
| **[!UICONTROL Remove]** | 任意の入力を右クリックし、「 」を選択します。 **[!UICONTROL Remove]** をクリックして、選択した入力から指標をクリアします。 |
| **[!UICONTROL Remove All]** | 右クリック *チャネル* を選択し、 **[!UICONTROL Remove All]** をクリックして、すべての入力指標をクリアします。 |
