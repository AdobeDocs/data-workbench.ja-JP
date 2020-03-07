---
description: 待ち時間テーブルのビジュアライゼーションは、待ち時間ディメンションを含むテーブルです。このディメンションは一種の派生ディメンションで、特定のイベントの発生から経過した時間を測定します。
solution: Analytics
title: 待ち時間テーブル
topic: Data workbench
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Latency tables{#latency-tables}

待ち時間テーブルのビジュアライゼーションは、待ち時間ディメンションを含むテーブルです。このディメンションは一種の派生ディメンションで、特定のイベントの発生から経過した時間を測定します。

1 つ以上のビジュアライゼーション内に選択範囲を作成し、イベントを設定コンテキストメニューオプションを使用してその選択範囲をイベントとして設定することにより、イベントを定義します。待ち時間テーブルは、時間との相関を探しているキャンペーンや特定の顧客の注文に関連するアクティビティの追跡に特に役立ちます。

[!DNL Site] では、待ち時間テーブルには、イベントの前またはイベントの後 7 日間に発生した訪問者セッションに関する情報が表示されますが、様々な可算ディメンションや時間ディメンションに関する情報を表示するように設定できます。See [Configuring Latency Tables](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

選択した特定のイベントの一部である、セッションなどの親ディメンションの要素の待ち時間はゼロです。その他すべての要素には、イベントからの（適切な時間ディメンションにおける）距離を反映した待ち時間が割り当てられます。

以下の例では、待ち時間テーブルの使用方法について説明します。

**キャンペーンに関連するバリューイベントの特定**

特定の広告キャンペーンに反応する前 7 日間および反応した後 7 日間の顧客のアクティビティを追跡するものとします。特定の広告キャンペーンの待ち時間を表示するには、関心のあるキャンペーンを待ち時間テーブルのイベントとして設定します。

以下のワークスペースの待ち時間は、キャンペーン 11566 という選択範囲（このキャンペーンに反応したセッション）に基づいています。

![](assets/vis_Latency.png)

「+0 日」という待ち時間は、キャンペーン 11566 に反応したセッションと、同じ日に発生した同じ顧客のその他すべてのセッションを識別します。

「-2 日」という待ち時間は、顧客がキャンペーンに反応する 2 日前に発生した、同じ顧客のセッションを識別します。

「+7 日」という待ち時間は、顧客がキャンペーンに反応した 7 日後に発生した、同じ顧客のセッションを識別します。

以降の節に示す手順に加え、要素の並べ替え、要素のマスク、シリーズの凡例の追加、データのエクスポートなど、テーブル内で実行できる作業と同じ作業をすべて実行できます。詳しくは、「 [テーブル](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## 待ち時間テーブルの作成 {#section-31a03031d9854ef7acc2462d4f37678d}

待ち時間テーブルを作成するには、まず選択範囲を作成し、待ち時間を追跡するイベントとしてその選択範囲を設定します。

1. ワークスペース内で右クリックし、目的のビジュアライゼーションを開きます。このビジュアライゼーションは、待ち時間テーブルの設定に使用する可算ディメンションに基づいている必要があります。

   例えば、[!DNL Site] では、ビジュアライゼーションはセッションベースである必要があります。

1. 空白の待ち時間テーブルを開きます。
1. ワークスペース内に選択範囲を作成します。
1. Right-click within the latency table and click **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>選択したイベントは、選択したイベントを待ち時間ディメンションとして保存しない限り保持されません。 手順については、「[待ち時間テーブルの再利用](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46)」を参照してください。

## 待ち時間テーブルの再利用 {#section-05f741169d204213b6537dce553e4f73}

同じ待ち時間テーブルを再利用する場合は、待ち時間テーブルをローカルに保存できます。適切な権限がある場合は、待ち時間テーブルをサーバーに保存して、特定のプロファイルのすべてのユーザーがアクセスできるようにすることも可能です。

**待ち時間テーブルを保存して他のワークスペースで使用できるようにするには**

1. Right-click the top border of the visualization and click **[!UICONTROL Save]**. The [!DNL Save] window appears. デフォルトの保存場所は、User\*profile name*\Workフォルダーです。
1. In the [!DNL File name] field, type a descriptive name for the visualization and click **[!UICONTROL Save]**.

**保存されている待ち時間テーブルを取得するには**

1. ワークスペース内で右クリックし、/をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL File]**&#x200B;す。 The [!DNL Open Visualization] window appears.
1. 保存した待ち時間テーブルに移動します。
1. Select the latency table visualization file ( [!DNL *.vw]) and click **[!UICONTROL Open]**.

## 待ち時間ディメンションの再利用 {#section-29c6483bf9ba476fb1c24ad1df253f46}

同じ待ち時間ディメンションを再利用する場合は、待ち時間ディメンションをローカルに保存できます。適切な権限がある場合は、待ち時間ディメンションをサーバーに保存して、特定のプロファイルのすべてのユーザーがアクセスできるようにすることも可能です。

Any latency dimensions that you create are saved in the profile’s Dimensions directory and are available in the [!DNL Change Dimension] drop-down list within Data Workbench.

**待ち時間ディメンションを保存して他のワークスペースで使用できるようにするには**

1. Right-click the [!DNL Latency] column label or one of its elements and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears.
1. Dimensions ディレクトリ内の適切なサブディレクトリを選択または作成します。
1. フィールド [!DNL File name] に、ディメンションを説明する名前（例：）を入力し、をク [!DNL Latency for Campaign 11565.dim]リックしま **[!UICONTROL Save]**&#x200B;す。

**保存されている待ち時間ディメンションを取得するには**

1. ワークスペース内で右クリックし、/をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL File]**&#x200B;す。 The [!DNL Open Visualization] window appears.
1. User\*profile name*\Dimensionsフォルダーに保存した待ち時間のビジュアライゼーションに移動します。
1. Select the latency dimension file ( [!DNL *.dim]) and click **[!UICONTROL Open]**.

## Microsoft Excelにエクスポート {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

ウィンドウの書き出しの詳細については、「ウィンドウデータの書き [出し」を参照してくださ](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)い。

## Export to a TSV file {#section-fd921f351c994ed0a94f63d3bd5b5a87}

ウィンドウの書き出しの詳細については、「ウィンドウデータの書き [出し」を参照してくださ](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)い。