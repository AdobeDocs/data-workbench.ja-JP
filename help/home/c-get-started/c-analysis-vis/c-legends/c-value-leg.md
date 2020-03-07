---
description: バリューの凡例には、定義済みのバリューイベントが表示されます。
solution: Analytics
title: バリューの凡例
topic: Data workbench
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Value legends{#value-legends}

バリューの凡例には、定義済みのバリューイベントが表示されます。

バリューの凡例は、HBX アプリケーションと [!DNL Site] アプリケーションでのみ設定できますが、他のアプリケーション用に設定することはできます。詳しくは、Adobe Consulting Services にお問い合わせください。

HBX および [!DNL Site] では、ビジネスバリューが生成されたセッションとしてバリューイベントが定義されます。例えば、特定のページビュー（「ご注文ありがとうございます」ページや申し込み完了ページなど）に関連付けられたイベントデータレコードは、企業にとってバリューイベントを表す場合があります。

バリューイベントを使用して、Web サイトで生成されたバリューの量を測定し、追跡できます。各イベントについてビジネスバリューを金額で評価し、次のような質問に答えられます。

* Web サイトの中で最も利益のあるパスはどれですか？
* 最も多くのバリューが生成されたリファラーまたはキャンペーンは何ですか？

凡例には、イベントごとに、イベントの単価（イベントあたりのバリュー）と、イベントによって生成されたバリューの総額が表示されます。この凡例を使用して、バリューイベントの定義や変更および単価の割り当てを行います。

次の表に、バリューイベントに関連する指標を示します。

| 指標 | 説明 |
|---|---|
| コンバージョン | ビジネスバリューが生成されたセッションの割合 |
| Value | 生成されたビジネスバリューの総額 |
| AverageValue | 生成されたビジネスバリューのセッションあたりの平均金額 |

訪問者が Web サイトで行うことなら何でも簡単にバリューイベントとして定義できます。例えば、顧客サービスリクエストの送信、申し込みの完了、コンテンツの表示、購入の完了などがあります。各バリューイベントは、Web サイト上の特定のページまたはページのセットにアクセスするユーザーに対応し、金額でビジネスバリューに関連付けられます。例えば、「お買い上げありがとうございます」ページに到達するユーザーごとに、平均 20 ドルの貢献利益が生成されるとします。その場合、そのページに対して、20 ドルのビジネスバリューがあるバリューイベントを定義します。

## 新しいバリューイベントの定義 {#section-2ea4d168336e4d2e98b22b636ed43853}

**HBX または[!DNL Site]**で新しいバリューイベントを定義するには

バリューイベントを作成する場合、バリューを表す Web サイトのページをビジュアライゼーションからバリューの凡例にドラッグします。

1. バリューの凡例を開きます。

   ![](assets/lgd_ValueLegend.png)

1. プロセスマップ、URI ページテーブルまたはページ階層ビューから凡例にバリューイベントを追加します。

   * プロセスマップからの場合、ノードをプロセスマップから凡例にドラッグします。
   * URI ページテーブルからの場合、Ctrl + Alt キーを押して、ページをテーブルから凡例にドラッグします。
   * ページ階層ビューからの場合、ノード（フォルダー、ページまたはグループ）の左をクリックして、凡例の上までドラッグします。
   ![](assets/client-leg.png)

   マウスが凡例に移動するまで、マウスポインターには「No」という文字が表示されます。

1. バリューの凡例で、イベントが発生するセッションごとにビジネスバリューを割り当てます。

   1. In the [!DNL Value per Event] column, click the cell that corresponds to the page you have added as a value event.
   1. そのイベントのバリューに割り当てる金額を入力して、Enter キーを押します。
   ![](assets/lgd_ValueLegend_Value.png)

   デフォルトでは、バリューイベントとして定義したページの URL がバリューの凡例に表示されます。必要に応じて、凡例内のこの URL をダブルクリックして編集モードに入り、イベントの名前を変更できます。また、いつでも特定のイベントの値を編集できます。Data Workbenchサーバーでは、平均値やコンバージョンなどの値イベントベースの指標が自動的に再計算されます。

少なくとも 1 つのバリューイベントを定義すると、Value Segment ディメンションが使用できるようになります。このディメンションは、訪問者がすべてのセッションで生成した総額を表します。

## バリューイベントの削除 {#section-25cd90a859384ca183c0fc0998f888cf}

* Right-click the desired event and click **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Data Workbenchサーバーは、使用しているプロファイルからアクセス可能なデータのセット全体にわたって指標を計算します。 By default, the [!DNL Data Workbench Server] calculates such metrics as Value, Value Events, Average Value, and Conversion across all data in the analysis dataset, even if the data is not from the same logical source.

## Microsoft Excelにエクスポート {#section-feaa7a8eb8124fafbc74169bebaed6d8}

ウィンドウの書き出しの詳細については、「ウィンドウデータの書き [出し」を参照してくださ](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)い。
