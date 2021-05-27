---
description: ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。
title: ブール演算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 59%

---

# ブール演算{#boolean-operations}

ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。

テスト演算について詳しくは、[テスト演算](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144)を参照してください。 [!DNL boolean]操作を定義する場合、操作の子を0個以上定義できます。

**ブール演算に子条件を追加するには**

1. [!DNL Boolean]操作に対応する名前または番号を右クリックします。
1. **[!UICONTROL Add new child]**&#x200B;をクリックし、追加する条件の種類を1つ選択します。
1. 手順1と2を繰り返し、[!DNL Boolean]操作に必要な子条件をすべて追加します。

   >[!NOTE]
   >
   >[!DNL Boolean]操作に対応する名前または番号を右クリックすると、[!DNL Add new sibling]メニューオプションが表示されます。 兄弟とは、右クリックした[!DNL Boolean]操作と同じ相対位置にある別の条件です。 [!DNL Boolean]操作の新しい兄弟を追加する操作は、[!DNL Condition]または[!DNL Log Entry Condition]パラメーターを右クリックして新しい条件を追加する操作と同じです。

**ブール演算から子条件を削除するには**

1. [!DNL Boolean]操作から削除する子条件の名前または子条件に対応する番号を右クリックします。
1. **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>をクリックします。numberは、削除する子条件に対応する番号です。

この節では、次の条件について説明します。

* [And](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Neither](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [または](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## And {#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And] 条件は、0 個以上の子条件を持つことができ、そのいずれの子ノードからも false が返されなかったときに true を返します。

[!DNL And] 条件は、Data Workbench サーバーにおけるすべての条件判定のルートとなる演算です。[!DNL And] 条件に子が存在しない場合、条件は true に評価されて、関連する処理が実行されます。アクションの条件判定として [!DNL And] 条件しか存在しなければ、そのアクションが必ず実行されることから、And は、すべての条件判定のルートとして使用されています。

次の例は、[!DNL And]条件を使用して、ログエントリの日付が2006年に発生し、リクエストされたページが[!DNL /products/purchase.asp]であった場合にのみ[!DNL Copy]変換を確実におこなう方法を示しています。

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

[!DNL Neither] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば false を返します。[!DNL Neither] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Neither] 条件は true に評価されます。

次の例では、[!DNL Neither] 条件の子として 2 つの [!DNL Range] 条件が存在します。この [!DNL Neither] 条件では、2007 年 1 月 1 日から 2007 年 1 月 10 日に発生したログエントリと、2007 年 1 月 12 日から 2007 年 1 月 14 日の期間に発生したログエントリとが除外されます。収集されたデータに問題のあったことがあらかじめわかっている期間のトランザクションをデータセットから除外するために、こうした条件を [!DNL Log Entry Condition] として使用することが考えられます。

![](assets/cfg_Condition_NeitherCondition.png)

## または {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば true を返します。[!DNL Or] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Or] 条件は false に評価されます。

この例では、[!DNL String Match]条件を持つ[!DNL Or]条件と、[!DNL Range]条件を子として示しています。 この [!DNL Or] 条件が満たされるのは、yes に設定された [!DNL x-hasproblem] 値がログエントリに含まれているか、または、ログエントリの発生日が 2007 年 1 月 1 日から 2007 年 1 月 10 日の期間に該当する場合のみです。

![](assets/cfg_Condition_OrCondition.png)
