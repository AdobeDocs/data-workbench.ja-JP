---
description: 変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。
title: 条件について
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 62%

---

# 条件について{#about-conditions}

{{eol}}

変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。

Log Entry Condition パラメーターでは、データセットの構築プロセスに含める必要のあるログエントリが、条件を使って判断されます。この付録では、Data Workbench サーバー内で使用可能な各種条件について説明します。

条件には、次の 2 つのカテゴリーがあります。

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]、および [!DNL String Match] 条件は、使用可能なログフィールドの様々な状態をテストするために使用されます。

* **[!DNL Boolean Operations]:** この [!DNL And], [!DNL Or]、および [!DNL Neither] 条件は、上記のテスト演算を組み合わせるために使用されます。 例えば、 [!DNL Range] 条件と [!DNL String Match] 適切なアクションを実行するには、両方とも false である必要がある条件を使用する場合、この 2 つの操作を [!DNL Neither] 条件。 [!DNL And] 条件は、システム内のすべての条件判定のルートとして使用されます。
