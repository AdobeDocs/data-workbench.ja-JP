---
description: ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。
title: ブール演算
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 59%

---

# ブール演算{#boolean-operations}

{{eol}}

ブール演算は、複数のテスト演算の結果を組み合わせるもので、テスト演算はブール演算の子として機能します。

テスト演算について詳しくは、 [テスト演算](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). 次の場合、 [!DNL boolean] 操作の場合は、操作に 0 個以上の子を定義できます。

**ブール演算に子条件を追加するには**

1. 名前または [!DNL Boolean] 操作。
1. クリック **[!UICONTROL Add new child]** をクリックし、追加する条件のタイプを 1 つ選択します。
1. 手順 1 と 2 を繰り返して、 [!DNL Boolean] 操作。

   >[!NOTE]
   >
   >名前または番号を右クリックすると、 [!DNL Boolean] 操作、 [!DNL Add new sibling] メニューオプション。 兄弟とは、条件階層内で [!DNL Boolean] をクリックします。 新しい兄弟の追加 [!DNL Boolean] 操作は、 [!DNL Condition] または [!DNL Log Entry Condition] パラメーター。

**ブール演算から子条件を削除するには**

1. 子条件の名前または削除する子条件に対応する番号を右クリックします [!DNL Boolean] 操作。
1. クリック **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>（ number は、削除する子条件に対応する数値）

このセクションでは、次の条件について説明します。

* [および](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Neither](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [または](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## および {#section-a14dba4b07cc4ab9aeb20868f773db7c}

[!DNL And] 条件は、0 個以上の子条件を持つことができ、そのいずれの子ノードからも false が返されなかったときに true を返します。

[!DNL And] 条件は、Data Workbench サーバーにおけるすべての条件判定のルートとなる演算です。[!DNL And] 条件に子が存在しない場合、条件は true に評価されて、関連する処理が実行されます。アクションの条件判定として [!DNL And] 条件しか存在しなければ、そのアクションが必ず実行されることから、And は、すべての条件判定のルートとして使用されています。

この例では、 [!DNL And] 条件は、 [!DNL Copy] 変換は、2006 年にログエントリの日付が発生し、リクエストされたページが [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

[!DNL Neither] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば false を返します。[!DNL Neither] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Neither] 条件は true に評価されます。

次の例では、[!DNL Neither] 条件の子として 2 つの [!DNL Range] 条件が存在します。この [!DNL Neither] 条件では、2007 年 1 月 1 日から 2007 年 1 月 10 日に発生したログエントリと、2007 年 1 月 12 日から 2007 年 1 月 14 日の期間に発生したログエントリとが除外されます。収集されたデータに問題のあったことがあらかじめわかっている期間のトランザクションをデータセットから除外するために、こうした条件を [!DNL Log Entry Condition] として使用することが考えられます。

![](assets/cfg_Condition_NeitherCondition.png)

## または {#section-a3aa0f56b6234f2680fa81939228326b}

[!DNL Or] 条件は、0 個以上の子条件を持つことができ、そのうち 1 つでも true に評価されるものがあれば true を返します。[!DNL Or] 条件に子が存在しなければ、子から true が返されることはありません。結果、[!DNL Or] 条件は false に評価されます。

この例では、 [!DNL Or] ～との条件 [!DNL String Match] 条件と [!DNL Range] 条件を子として設定します。 この [!DNL Or] 条件が満たされるのは、yes に設定された [!DNL x-hasproblem] 値がログエントリに含まれているか、または、ログエントリの発生日が 2007 年 1 月 1 日から 2007 年 1 月 10 日の期間に該当する場合のみです。

![](assets/cfg_Condition_OrCondition.png)
