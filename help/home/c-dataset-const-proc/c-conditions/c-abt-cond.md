---
description: 変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。
solution: Analytics
title: 条件について
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 条件について{#about-conditions}

変換とディメンションでは、ログフィールドに特定の命令やアクションを適用するタイミングが、条件を使って判断されます。

Log Entry Condition パラメーターでは、データセットの構築プロセスに含める必要のあるログエントリが、条件を使って判断されます。この付録では、Data Workbench サーバー内で使用可能な各種条件について説明します。

条件には、次の 2 つのカテゴリーがあります。

* **[!DNL Test Operations]:**[!DNL Compare]、、、、[!DNL Not Empty]お[!DNL Range][!DNL Regular Expression][!DNL String Match]よび各条件を使用して、利用可能なログフィールドの様々な状態をテストします。

* **[!DNL Boolean Operations]:**前述の[!DNL And]テス[!DNL Or]ト操作を組み[!DNL Neither]合わせるには、、、およびの条件を使用します。 For example, if you have a[!DNL Range]condition and a[!DNL String Match]condition that must both be false to take the appropriate action, you would make these two operations children of the[!DNL Neither]condition.[!DNL And]条件は、システム内のすべての条件判定のルートとして使用されます。

