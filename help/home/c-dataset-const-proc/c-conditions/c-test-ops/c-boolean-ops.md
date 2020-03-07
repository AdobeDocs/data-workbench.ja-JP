---
description: ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。
solution: Analytics
title: ブール演算
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ブール演算{#boolean-operations}

ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。

For information about the test operations, see [Test Operations](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). When you define a [!DNL boolean] operation, you can define zero or more children for the operation.

**ブール演算に子条件を追加するには**

1. Right-click the name or the number corresponding to the [!DNL Boolean] operation.
1. Click **[!UICONTROL Add new child]** and choose one of the available condition types to add.
1. Repeat steps 1 and 2 until you have added all of the desired child conditions for the [!DNL Boolean] operation.

   >[!NOTE]
   >
   >When you right-click the name or the number corresponding to a [!DNL Boolean] operation, you see the [!DNL Add new sibling] menu option. A sibling is another condition at the same relative position in the condition hierarchy as the [!DNL Boolean] operation that you right-clicked. Adding a new sibling for a [!DNL Boolean] operation is the same as adding a new condition by right-clicking the [!DNL Condition] or [!DNL Log Entry Condition] parameter.

**ブール演算から子条件を削除するには**

1. Right-click the name of the child condition or the number corresponding to the child condition that you want to remove from the [!DNL Boolean] operation.
1. Click **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, where number is the number corresponding to the child condition that you want to remove.

この節では、次の条件について説明します。

* [And](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Neither](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [または](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## AND {#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And] 条件は、0 個以上の子条件を持つことができ、そのいずれの子ノードからも false が返されなかったときに true を返します。

[!DNL And] 条件は、Data Workbench サーバーにおけるすべての条件判定のルートとなる演算です。[!DNL And] 条件に子が存在しない場合、条件は true に評価されて、関連する処理が実行されます。アクションの条件判定として [!DNL And] 条件しか存在しなければ、そのアクションが必ず実行されることから、And は、すべての条件判定のルートとして使用されています。

This example shows how an [!DNL And] condition is used to make sure that the [!DNL Copy] transformation occurs when only both the date of the log entry occurred in the year 2006 and that the page requested was [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

[!DNL Neither] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば false を返します。[!DNL Neither] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Neither] 条件は true に評価されます。

次の例では、[!DNL Neither] 条件の子として 2 つの [!DNL Range] 条件が存在します。この [!DNL Neither] 条件では、2007 年 1 月 1 日から 2007 年 1 月 10 日に発生したログエントリと、2007 年 1 月 12 日から 2007 年 1 月 14 日の期間に発生したログエントリとが除外されます。収集されたデータに問題のあったことがあらかじめわかっている期間のトランザクションをデータセットから除外するために、こうした条件を [!DNL Log Entry Condition] として使用することが考えられます。

![](assets/cfg_Condition_NeitherCondition.png)

## または {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば true を返します。[!DNL Or] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Or] 条件は false に評価されます。

This example shows the [!DNL Or] condition with a [!DNL String Match] condition and a [!DNL Range] condition as its children. この [!DNL Or] 条件が満たされるのは、yes に設定された [!DNL x-hasproblem] 値がログエントリに含まれているか、または、ログエントリの発生日が 2007 年 1 月 1 日から 2007 年 1 月 10 日の期間に該当する場合のみです。

![](assets/cfg_Condition_OrCondition.png)

