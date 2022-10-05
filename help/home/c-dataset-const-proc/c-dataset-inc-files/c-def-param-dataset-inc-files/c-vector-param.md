---
description: ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。
title: ベクターパラメーター
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 67%

---

# ベクターパラメーター{#vector-parameters}

{{eol}}

ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。

ベクトルパラメーターは、単独のベクトル項目としてのみ参照できます。この例では、 [!DNL Transformation Dataset Include] ベクトルパラメーターを定義するファイル。 ベクトルパラメーターである「Internal Domains」は 3 つの値から成ります。

![](assets/cfg_WebParameters_InternalDomains.png)

このベクトルパラメーターは、[!DNL Matches] 条件の [!DNL String Match] ベクトルにリストされている唯一の項目であることに注目してください。

![](assets/cfg_Parameters_InternalDomains_Ref.png)

内部ドメインについて詳しくは、 [Web データの設定](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). 詳しくは、 [!DNL String Match] 条件については、 [条件](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
