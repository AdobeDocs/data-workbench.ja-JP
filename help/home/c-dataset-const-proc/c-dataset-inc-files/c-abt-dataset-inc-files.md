---
description: アプリケーションとともに提供される内部プロファイルには、多くの場合、それぞれ独自のデータセット設定ファイルが付属します。
solution: Analytics
title: データセットインクルードファイルについて
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データセットインクルードファイルについて{#about-dataset-include-files}

アプリケーションとともに提供される内部プロファイルには、多くの場合、それぞれ独自のデータセット設定ファイルが付属します。

内部プロファイルはデータセットプロファイルの下位プロファイルなので、データセット構築におけるログの処理段階や変換段階で別途必要となるパラメーターを規定したルールは、そのデータセット設定ファイルに含まれています。内部プロファイルのデータセット設定ファイルや、継承によって独自に作成したプロファイルのデータセット設定ファイルを「データセットインクルードファイル」といいます。

データセットインクルードファイルに含まれているのは、データセットプロファイルのメインのデータセット設定ファイル（[!DNL Log Processing.cfg] または [!DNL Transformation.cfg]）に含まれているパラメーターのサブセットです。ログ処理に関連するパラメーターを含むデータセットインクルードファイルは [!DNL Log Processing Dataset Include] 、ファイルと呼ばれます( [Log Processing Dataset Include Filesを参照](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab))。変換に関連するデータセットインクルードファイルは、 [!DNL Transformation Dataset Include] Filesと呼ばれます。 変換データセ [ットインクルードファイルを参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)い。 データセット構築プロセスに使用するデータセットインクルードファイルは複数作成できます。完成したデータセットには、データセットプロファイルと継承プロファイルの全データセット設定ファイルに定義されているフィールド、変換、拡張ディメンションがすべて追加されます。
