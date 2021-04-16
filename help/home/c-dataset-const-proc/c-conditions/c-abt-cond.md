---
description: 変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。
title: 条件について
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 62%

---

# 条件について{#about-conditions}

変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。

Log Entry Condition パラメーターでは、データセットの構築プロセスに含める必要のあるログエントリが、条件を使って判断されます。この付録では、Data Workbench サーバー内で使用可能な各種条件について説明します。

条件には、次の 2 つのカテゴリーがあります。

* **[!DNL Test Operations]:** [!DNL Compare]、、 [!DNL Not Empty]、 [!DNL Range]、 [!DNL Regular Expression]、 [!DNL String Match] および条件を使用して、利用可能なログフィールドの様々な状態をテストします。

* **[!DNL Boolean Operations]:**  [!DNL And]、 [!DNL Or]および [!DNL Neither] 条件を使用して、上記のテスト演算を組み合わせます。例えば、[!DNL Range]条件と[!DNL String Match]条件があり、両方ともfalseに設定して適切なアクションを実行する必要がある場合、[!DNL Neither]条件の子としてこの2つの操作を作成します。 [!DNL And] 条件は、システム内のすべての条件判定のルートとして使用されます。
