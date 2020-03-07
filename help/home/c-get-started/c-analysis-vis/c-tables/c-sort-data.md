---
description: データを並べ替える手順です。
solution: Analytics
title: テーブル内のデータの並べ替え
topic: Data workbench
uuid: 66869478-922d-41e1-915d-3ed7bff3b08d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# テーブル内のデータの並べ替え{#sort-data-in-a-table}

データを並べ替える手順です。

テーブルにディメンションが 1 つだけ存在する場合は、指標のラベルをクリックするだけで、その指標に基づいてデータを並べ替えられます。

1. Right-click an element or the label of the dimension that you want to sort and click **[!UICONTROL Sort]**.

   ![](assets/mnu_Table_Sort.png)

1. 次のいずれかのオプションをクリックします。

   * **[!UICONTROL By ordinal]** を使用して、要素の自然な順序に従って要素を並べ替えます。 例えば、Hour ディメンションの要素は暦の順に表示されます。ディメンションに自然な順序がない場合（リファラーや URI などの場合）、この並べ替え順は有用ではないので、アルファベット順または指標別の並べ替えを選択する必要があります。
   * **[!UICONTROL Alphabetically]** エレメント名のアルファベット順にディメンションを並べ替える場合。
   * **[!UICONTROL By metric]** をクリックして、データの並べ替えに使用する指標を選択します。 例えば、リファラーディメンションをセッション指標で並べ替えて、サイト上の最も多くのセッションに貢献するリファラーを確認できます。

      指標で並べ替える場合、デフォルトでは、その時の選択によって影響を受けた指標の値に対応して、テーブル内の順序が決まります。後で選択を変更しても、ディメンションを並べ替えるか、動的選択を有効にしない限り、並べ替え順序は元の順序から変わりません。When you click **[!UICONTROL Sort]** > **[!UICONTROL Dynamic Selection]**, the table is resorted each time you change the selection.
   テーブル内の既存の指標で並べ替えるには、指標のラベルをクリックします。

1. (Optional) To choose whether to sort in ascending or descending order, right-click an element or the label of the dimension that you want to sort and click **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Ascending]** or **[!UICONTROL Sort]** > **[!UICONTROL Order]** > **[!UICONTROL Descending]**.

   テーブルにディメンションが 1 つだけ存在する場合、指標のラベルをクリックするだけで、並べ替え順序を逆にできます。ラベルをもう一度クリックすると並べ替え順序が逆になります。

