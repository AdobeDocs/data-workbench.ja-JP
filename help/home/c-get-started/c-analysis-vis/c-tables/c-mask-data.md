---
description: マスクとは、データのサブセットまたはディメンション内の要素のサブセットを選択することです。
title: データのマスク
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 66%

---

# データのマスク{#mask-data}

{{eol}}

マスクとは、データのサブセットまたはディメンション内の要素のサブセットを選択することです。

分析に含めたくない要素をマスクまたは非表示にします。

Data Workbenchには、ディメンション要素をマスクする 2 つの方法が用意されています。 1 つ目の方法では、 [!DNL Mask] メニュー の使用 [!DNL Mask] メニューオプションを使用すると、マウスを使用して表示またはマスクする要素を選択したり、指標でデータを並べ替える際にトップランクの要素を表示したりできます。 ディメンション要素をマスクする第二の方法では、検索を使用します。

**データをマスクするには**

1. 目的のディメンションの要素またはラベルを右クリックし、 **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. 次のいずれかのオプションをクリックします。

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]**&#x200B;または **[!UICONTROL 500]** 指標で並べ替えられた表示される要素の
   * **[!UICONTROL Show top > All Positive]** ゼロ (0) より大きい値のみを表示するには
   * **[!UICONTROL Display “X more”]** 現在マスクされている要素の数を表示するには
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*（非正規ディメンションを使用する場合にのみ使用できます）

      非正規ディメンションを使用している場合、このオプションを選択すると、可算ディメンションでディメンションをマスクできます。このオプションを選択すると、選択した可算ディメンションの要素を 1 つ以上持つ要素のみがテーブルに表示されます。テーブルには最大 1,023 個の要素が表示されます。

>[!NOTE]
>
>Adobe [!DNL Platform] では、データがランダムな順序で処理されます。少なくとも 1 つのマスキングで 1,023 個を超える要素が生成される場合、より一般的で大きな要素は、テーブルに含まれる可能性が高くなります。

「トップ」または「1 つ以上」でマスクすると、デフォルトでは、テーブル内の順序はその時点での選択範囲に影響を受けた値に対応します。後で選択範囲を変更した場合、テーブルを再度並べ替えるか、動的選択を有効にしない限り、順序はオリジナルの順序から変更されません。クリック時 **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**&#x200B;を指定した場合、選択を変更するたびにテーブルが並べ替えられます。

**検索を使用してデータをマスクするには**

* 以下の検索オプションのどちらかを使用して、データをマスクできます。

   * 目的のディメンションの要素またはラベルを右クリックし、 **[!UICONTROL Mask]**&#x200B;を、 [!DNL Search] ボックスに、検索する語句を入力します。

      ![](assets/mnu_Table_MaskSearch.png)

   * 目的のディメンションの要素またはラベルを右クリックし、 **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**&#x200B;をクリックし、ディメンションラベルセルに表示される検索ボックスに、検索する語句を入力します。

      ![](assets/vis_Table_Mask_searchBar.png)

      検索フレーズを入力すると、Data Workbenchは一致を反映するようにディメンションを更新します。

以下の方法を使用して、検索時のマスキングをさらに制約できます。

* 「re:」と「 [!DNL search] 検索フレーズを正規表現として解釈するためのボックスまたはバー。 正規表現に関連付けられた任意の構文を検索フレーズに使用できます。正規表現について詳しくは、『*データセット設定ガイド*』の付録「正規表現」を参照してください。
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
