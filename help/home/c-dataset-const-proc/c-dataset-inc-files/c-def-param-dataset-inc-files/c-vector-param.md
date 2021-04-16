---
description: ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。
title: ベクターパラメーター
uuid: 2ca83502-acc4-4b94-b0e4-a48a596e7623
exl-id: c6140bdf-dcd9-4fa9-a6e0-34cbc45414d0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 67%

---

# ベクターパラメーター{#vector-parameters}

ベクトルパラメーターには、1 つの変数につき複数の値が格納されます。

ベクトルパラメーターは、単独のベクトル項目としてのみ参照できます。次の例は、ベクトルパラメーターを定義する[!DNL Transformation Dataset Include]ファイルを示しています。 ベクトルパラメーターである「Internal Domains」は 3 つの値から成ります。

![](assets/cfg_WebParameters_InternalDomains.png)

このベクトルパラメーターは、[!DNL Matches] 条件の [!DNL String Match] ベクトルにリストされている唯一の項目であることに注目してください。

![](assets/cfg_Parameters_InternalDomains_Ref.png)

内部ドメインについて詳しくは、[Webデータの構成設定](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)を参照してください。 [!DNL String Match]条件について詳しくは、[条件](../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)を参照してください。
