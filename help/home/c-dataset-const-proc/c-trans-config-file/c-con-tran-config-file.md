---
description: Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。
solution: Analytics
title: 変換設定ファイルに関する考慮事項
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 変換設定ファイルに関する考慮事項{#considerations-for-the-transformation-configuration-file}

Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。

* このファイルに含まれるいずれかのパラメーターを変更した場合、データの再変換が必要となります。
* If you reprocess the data, you can check the [!DNL Transformation Progress] parameter in data workbench&#39;s [!DNL Processing Legend].

   データの再処理について詳しくは、「再処理と再変換」 [!DNL Processing Legend,] を参 [照してください](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL CrossRows]、、、 [!DNL ODBCLookup]お [!DNL Sessionize]よび変 [!DNL AppendURI] 換は、ファイル内で定義されている場合にのみ機能 [!DNL Transformation Dataset Configuration] します。 これらの変換について詳しくは、データ変換を参 [照してください](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

   >[!NOTE]
   >
   >Adobe recommends defining transformations for the transformation phase of dataset construction in one or more [!DNL Transformation Dataset Include] files. 詳しくは、変換データセットインクルードフ [ァイル(英語のみ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace))を参照してください。

* 前述のパラメーターはいずれも [!DNL Transformation.cfg] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

   Any errors that occur during the transformation phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

