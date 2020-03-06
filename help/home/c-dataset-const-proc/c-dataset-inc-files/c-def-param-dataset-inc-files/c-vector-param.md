---
description: ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。
solution: Analytics
title: ベクトルパラメーター
topic: Data workbench
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ベクトルパラメーター{#vector-parameters}

ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。

ベクトルパラメーターは、単独のベクトル項目としてのみ参照できます。This example shows a [!DNL Transformation Dataset Include] file that defines a vector parameter. ベクトルパラメーターである「Internal Domains」は 3 つの値から成ります。

![](assets/cfg_WebParameters_InternalDomains.png)

このベクトルパラメーターは、[!DNL Matches] 条件の [!DNL String Match] ベクトルにリストされている唯一の項目であることに注目してください。

![](assets/cfg_Parameters_InternalDomains_Ref.png)

内部ドメインについて詳しくは、「Webデータの [設定」を参照してください](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。 条件について詳しくは、「 [!DNL String Match] 条件」を参照して [ください](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。
