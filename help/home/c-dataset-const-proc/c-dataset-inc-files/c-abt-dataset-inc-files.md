---
description: アプリケーションとともに提供される内部プロファイルには、多くの場合、それぞれ独自のデータセット設定ファイルが付属します。
title: データセットインクルードファイルについて
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 82%

---

# データセットインクルードファイルについて{#about-dataset-include-files}

{{eol}}

アプリケーションとともに提供される内部プロファイルには、多くの場合、それぞれ独自のデータセット設定ファイルが付属します。

内部プロファイルはデータセットプロファイルの下位プロファイルなので、データセット構築におけるログの処理段階や変換段階で別途必要となるパラメーターを規定したルールは、そのデータセット設定ファイルに含まれています。内部プロファイルのデータセット設定ファイルや、継承によって独自に作成したプロファイルのデータセット設定ファイルを「データセットインクルードファイル」といいます。

データセットインクルードファイルに含まれているのは、データセットプロファイルのメインのデータセット設定ファイル（[!DNL Log Processing.cfg] または [!DNL Transformation.cfg]）に含まれているパラメーターのサブセットです。ログ処理に関連するパラメーターを含むデータセットインクルードファイルは、 [!DNL Log Processing Dataset Include] ファイル ( [ログ処理データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)) の代わりに、変換に関連付けられたデータセットインクルードファイルが呼び出されます [!DNL Transformation Dataset Include] ファイル。 詳しくは、 [変換データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). データセット構築プロセスに使用するデータセットインクルードファイルは複数作成できます。完成したデータセットには、データセットプロファイルと継承プロファイルの全データセット設定ファイルに定義されているフィールド、変換、拡張ディメンションがすべて追加されます。
