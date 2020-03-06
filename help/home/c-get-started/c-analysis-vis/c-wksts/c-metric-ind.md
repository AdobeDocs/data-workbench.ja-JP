---
description: ワークシートを使用して、指標が定義済みのしきい値に達したことを示せます。
solution: Analytics
title: 指標インジケーターの作成
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 指標インジケーターの作成{#create-a-metric-indicator}

ワークシートを使用して、指標が定義済みのしきい値に達したことを示せます。

In addition, you can use [!DNL Report] to automatically generate and distribute a report when a metric reaches a defined threshold within a specified time frame.

For more information about [!DNL Report], see the *Data Workbench Report Guide*.

* [上昇または下降インジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [チェックインジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**ワークシートを使用して指標インジケーターを作成するには**

1. ワークシートのセルの内容を定義します。

   1. 列 A に目的の指標の名前（[!DNL Visitors] など）を入力します。
   1. In Column B, enter the value of the desired metric (for example, [!DNL =Visitors]).
   1. 列 C に指標の低しきい値を入力します。
   1. 列 D に指標の高しきい値を入力します。
   1. 列 E に適切な数式を入力します。例については、「[上昇または下降インジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)」または「[チェックインジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)」を参照してください。
   1. In the formula cell (Column E), right-click and click **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, then click one of the following:

      * **[!UICONTROL None]**:インジケーターの代わりに正確な計算を表示します。
      * **[!UICONTROL Check]**:チェックマークまたはXを使用して、数式に応じて、値が設定したしきい値を超えているか、下回っているかを示します。 「[チェックインジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)」を参照してください。
      * **[!UICONTROL Up or Down]**:上向き矢印または下向き矢印を使用して、値が低しきい値（下向き矢印）を下回るか、高しきい値（上向き矢印）を上回るか、低しきい値と高しきい値（空白）の間にあるかを示します。 「[上昇または下降インジケーター](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)」を参照してください。

1. インジケーターを作成する他の指標に対して手順 1 を繰り返します。

作成されたワークシートは、次の例のようになります。

![](assets/vis_Worksheet_Alerts.png)

## Up or down indicator {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

またはに [!DNL Up] は、次 [!DNL Down indicator]の数式を使用します。

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

次に例を示します。[!DNL =(b2-c2)/(d2-c2)*2-1]

Three outcomes are possible for each metric when using this formula with the [!DNL Up] or [!DNL Down indicator]:

* 指標の値が低しきい値と高しきい値の間にある場合、数式は -1 と 1 （これらの値を含まない）の間の数値に評価されます。ワークシートに上向き矢印または下向き矢印は表示されません。
* 指標の値が低しきい値以下の場合、数式は -1 以下の値に評価されます。指標インジケーターが下向き矢印に変わります。
* 指標の値が高しきい値以上の場合、数式は 1 以上の値に評価されます。指標インジケーターが上向き矢印に変わります。

The following worksheet illustrates what the example formula [!DNL =(b2-c2)/(d2-c2)*2-1] would display:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Check indicator {#section-98c5298a74f34dcbaaf151549fcc7090}

For the [!DNL Check indicator], you use a formula that indicates whether you want to be notified when the metric value is above or below the threshold you specify. 次に例を示します。

* 値が設定したしきい値を下回ったら通知する場合は、以下の数式を使用できます。

   * [!DNL threshold - metric]

      次に例を示します。[!DNL =(c2-b2)]

* 値が設定したしきい値を上回ったら通知する場合は、以下の数式を使用できます。

   * [!DNL metric - threshold]

      次に例を示します。[!DNL =(b3-c3)]

チェックマークが表示される場合、数式は正数に評価されます。X が表示される場合、数式は負数に評価されます。

There are two possible outcomes for each metric when using the [!DNL Check indicator]:

* 指標の値をしきい値より上に保つことが望ましいということを数式が示す場合、指標の値がしきい値以上であればチェックマークが表示され、しきい値未満であれば X が表示されます。
* 指標の値をしきい値より下に保つことが望ましいということを数式が示す場合、指標の値がしきい値以下であればチェックマークが表示され、しきい値より大きければ X が表示されます。

The following worksheet illustrates what the example formulas [!DNL =(c2-b2)] and [!DNL =(b3-c3)] would display:

![](assets/vis_Worksheet_Alerts_Check.png)

