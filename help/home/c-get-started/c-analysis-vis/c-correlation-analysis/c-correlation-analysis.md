---
description: 統計的相関では、高度なデータマイニングにより、意味のある関係を測定して、機会を特定します。
title: 相関行列
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 79%

---

# 相関行列{#correlation-matrix}

{{eol}}

統計的相関では、高度なデータマイニングにより、意味のある関係を測定して、機会を特定します。

を使用する [ピアソン相関係数](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)を使用すると、マーケティングキャンペーンの次のステップの特定、サイトデザインの改善、追加の相関依存関係に関する詳細な顧客分析の継続に役立つ関連情報を提供できます。

## 相関行列の作成 {#section-87ed12ccc1af4196a1b6534e621c4cbb}

相関行列では、可算または非可算ディメンションに対して指標を比較します。その後、行列を変更して、色の選択によってビジュアライゼーション内の相関関係を強調したり、テキストマップ、ヒートマップまたはその両方としてレンダリングしたりできます。

1. 相関行列を開きます。

   右クリック [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. ディメンションテーブルが開きます。

   ![](assets/correlation_matrix_2.png)

   次のようなディメンションを選択します。 [!DNL Time] > [!DNL Day of the Week] を選択します。 相関テーブルが開き、行列の隅にディメンションが表示され、行と列に関連する指標が配置されます。曜日ディメンションの場合、 **[!UICONTROL Visits]** は関連する指標です。

   ![](assets/correlation_matrix_1.png)

   指標をその指標自体と比較しているので、相関関係は 1.000 です（完全だが使用できない相関関係を表しています）。

1. 指標の 1 つを変更します。

   右クリックして「 」を選択します。 **[!UICONTROL Change Metric]** をクリックして、行または列の指標を変更します。 これにより、2 つの指標の値の相関関係が設定されます。

   この例では、 **[!UICONTROL Visits]** 列の指標 **[!UICONTROL Internal Searches]**. 右クリックして「 」を選択します。 [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. 相関行列に複数の指標を追加します。

   指標の列または行を右クリックします。例えば、指標メニューから、 [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   新しい指標が相関値と共に列に表示されます。他の指標 ( **[!UICONTROL Email Signups]**&#x200B;をクリックし、テーブルを作成します。

   ![](assets/correlation_matrix_6.png)

   または、列の指標と比較する指標を行に追加します。

   ![](assets/correlation_matrix_add_metric.png)

1. （オプション）ディメンションエレメントを追加して、指標を制限します。

   ワークスペース内で右クリックし、「 」を選択します。 **[!UICONTROL Table]**. 開いているディメンションテーブルで、Ctrl + Alt キーを押しながらエレメントを列または行の指標の上にドラッグします。エレメントがブラケットに囲まれて指標の横に表示されます。

   例えば、 **[!UICONTROL Visits]** 指標を使用する場合は、「 **[!UICONTROL Country]** as **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   ディメンションエレメントを選択すると、選択したディメンションエレメントに基づいてすべての指標の相関関係が変更されることに注意してください。ディメンションウィンドウを閉じると、訪問回数指標だけが「New Zealand（ニュージーランド）」に制約されるようになります。

   >[!NOTE]
   >
   >ディメンション制約を使用して指標を変更する場合（右クリックし、「 」を選択する） **[!UICONTROL Change Metric]**) の場合、指標を制限するディメンション要素は失われます。 その場合は、ディメンションエレメントを再度追加する必要があります。

1. 指標をさらに制限する[バイナリフィルター](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c)を作成します。テーブル内の指標を右クリックし、メニューから「バイナリフィルター」を選択します。

## 相関関係の計画と分析の目的 {#section-cc322da60b7e417ba29e72b0afeb6f79}

相関行列を作成する一般的な目的は、次のとおりです。

**指定されたディメンションに対して 2 つの指標の関係を特定します**。この例では、相関行列はコアディメンションである曜日を中心に作成され、訪問回数、電子メールのサインアップ、サインインエラー指標を、内部検索、ログイン、表示された調査という指標イベントに対して比較しています。

**仮説を立てて、分析に集中します**。相関分析を実行したら、次は、指標の依存関係と相関関係を探します。例えば、内部検索が電子メールのサインアップに影響があることがわかれば、その関係を予測し、マーケティングキャンペーンや Web サイトのナビゲーションデザインを変更するといった対策を取ることができます。

**より高度なデータマイニングアルゴリズムが含まれている指標を特定します**。ほとんどの場合、重要な指標は、複数の相関関係に影響していることで特定されます。そうした重要な指標を選択し、追加のデータマイニング分析に適用して、より深く把握することができます。

## 相関行列機能の注意点 {#section-ef3626c665ea468a9ecdad624b4132f5}

**テーブル内のディメンションエレメントをフィルターおよび選択して、値のように比較します**。例えば、曜日ディメンションを使用していて、曜日ディメンションテーブル内の特定の曜日をクリックするなど、コアディメンションの要素をクリックすると、使用可能な相関がない、1 対 1 の一致が 100 ％で描画されます。ルートディメンションが曜日なので、曜日ディメンションテーブル内で選択すると、行列は 1 対 1 の相関に変更されます。

![](assets/correlation_matrix_10.png)

ただし、（すべてのエレメントから 1 つ選択した場合の）1 対 1 の相関関係はその特定の日に限られます。複数選択した場合は、必ずしも 1 対 1 の相関関係が残らず、選択した曜日が 1 つでも、1 つ以上でも、100％の一致がレンダリングされるとは限りません。

**統計的相関は、相関するデータモデルとは異なります**（Adobe Analytics 製品の過去の参照）。Data Workbench の統計的相関は、[ピアソン相関モデル](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)に基づいています。

**散布グラフで相関を表示します**。散布グラフのタイトルを右クリックし、「 」を選択します。 [!DNL Display Correlation] から [!DNL Visualization] メニュー 相関値が散布グラフの右上のセクションに表示されます。

>[!NOTE]
>
>アプリケーションがピアソン相関計算を実行できない場合、散布グラフとピアソン行列に「計算エラー」が表示されます。 これは、通常、データ不足により、0 で除算しようとする式が原因です。
