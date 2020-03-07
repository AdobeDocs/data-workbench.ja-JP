---
description: マスクとは、データのサブセットまたはディメンション内の要素のサブセットを選択することです。
solution: Analytics
title: データのマスク
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データのマスク{#mask-data}

マスクとは、データのサブセットまたはディメンション内の要素のサブセットを選択することです。

分析に含めたくない要素をマスクまたは非表示にします。

Data Workbenchには、ディメンション要素をマスクする2つの方法が用意されています。 The first method employs the options available in the [!DNL Mask] menu. Using the [!DNL Mask] menu options, you can use your mouse to select those elements to show or to mask, or you can show top-ranked elements when you sort the data by metric. ディメンション要素をマスクする第二の方法では、検索を使用します。

**データをマスクするには**

1. Right-click an element or the label of the desired dimension and click **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. 次のいずれかのオプションをクリックします。

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**&#x200B;または指標で並べ **[!UICONTROL 500]** 替えられた表示された要素の
   * **[!UICONTROL Show top > All Positive]** ゼロ(0)より大きい値のみを表示するには
   * **[!UICONTROL Display “X more”]** 現在マスクされている要素の数を表示するには
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*（非正規ディメンションを使用する場合のみ使用可能）

      非正規ディメンションを使用している場合、このオプションを選択すると、可算ディメンションでディメンションをマスクできます。このオプションを選択すると、選択した可算ディメンションの要素を 1 つ以上持つ要素のみがテーブルに表示されます。テーブルには最大 1,023 個の要素が表示されます。

>[!NOTE]
>
>Because the Adobe [!DNL Platform] processes data in random order, when At least one masking results in more than 1,023 elements, the more common and larger elements have a greater chance of being included in the table.

「トップ」または「1 つ以上」でマスクすると、デフォルトでは、テーブル内の順序はその時点での選択範囲に影響を受けた値に対応します。後で選択範囲を変更した場合、テーブルを再度並べ替えるか、動的選択を有効にしない限り、順序はオリジナルの順序から変更されません。When you click **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, the table is resorted each time you change the selection.

**検索を使用してデータをマスクするには**

* 以下の検索オプションのどちらかを使用して、データをマスクできます。

   * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]**, then in the [!DNL Search] box type the phrase for which you want to search.

      ![](assets/mnu_Table_MaskSearch.png)

   * Right-click an element or the label of the desired dimension, click **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, then in the search box that displays in the dimension label cell, type the phrase for which you want to search.

      ![](assets/vis_Table_Mask_searchBar.png)

      検索フレーズを入力すると、Data Workbenchは一致を反映するようにディメンションを更新します。

以下の方法を使用して、検索時のマスキングをさらに制約できます。

* You can type “re:” in the [!DNL search] box or bar to have the search phrase interpreted as a regular expression. 正規表現に関連付けられた任意の構文を検索フレーズに使用できます。正規表現について詳しくは、『*データセット設定ガイド*』の付録「正規表現」を参照してください。
* 記号 $ を検索文字列の先頭文字として入力すると、入力した文字列で始まるフレーズを探せます。検索文字列の最終文字として入力すると、入力した文字列で終わるフレーズを探せます。
* スペースを検索文字列の先頭文字として入力すると、入力した文字列で始まるフレーズ内の任意の単語を探せます。検索文字列の最終文字として入力すると、入力した文字列で終わるフレーズ内の任意の単語を探せます。

検索に文字列「on」を使用してテーブルをマスクする様々な方法の例を以下に示します。

* 「on」と入力すると、フレーズ内の任意の場所に文字列「on」を含むすべてのフレーズが表示されます。例：「**on** line banking」、「c **on** tact buyers」、「bulli **on** coins」、「bank **on** line」、「gold opti **on** s」、「silver bulli **on**」
* 「$on」と入力すると、文字列「on」で始まるすべてのフレーズが表示されます。例：

   「**on** line banking」、「**on**-line payment」

* 「on$」と入力すると、文字列「on」で終わるすべてのフレーズが表示されます。例：

   「silver bulli **on**」、「gold opti **on**」

* 「 on」と入力すると、文字列「on」で始まる単語を含むすべてのフレーズが表示されます。例：

   「**on** line banking」、「bank **on** line」

* 「on 」と入力すると、文字列「on」で終わる単語を含むすべてのフレーズが表示されます。例：

   「bulli **on** coins」、「silver bulli **on**」

* 「 on 」を使用すると、文字列「on」を単語として含むすべてのフレーズが表示されます。例：

   「**on** line banking」、「bank **on** line」

