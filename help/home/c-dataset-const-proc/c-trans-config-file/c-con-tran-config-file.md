---
description: Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。
title: 変換設定ファイルに関する考慮事項
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 49%

---

# 変換設定ファイルに関する考慮事項{#considerations-for-the-transformation-configuration-file}

{{eol}}

Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。

* このファイルに含まれるいずれかのパラメーターを変更した場合、データの再変換が必要となります。
* データを再処理する場合は、 [!DNL Transformation Progress] data workbench のパラメーター [!DNL Processing Legend].

   ：データの再処理に関する情報 [!DNL Processing Legend,] 参照 [再処理と再変換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]、および [!DNL AppendURI] 変換は、 [!DNL Transformation Dataset Configuration] ファイル。 これらの変換について詳しくは、 [データ変換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobeでは、データセット構築の変換段階で変換を定義する場合、1 つ以上の方法を使用することをお勧めします [!DNL Transformation Dataset Include] ファイル。 詳しくは、 [変換データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* 前述のパラメーターはいずれも [!DNL Transformation.cfg] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

   データセットプロファイルのデータセット構築プロセスの変換段階で発生したエラーは、次の表に示します。 [!DNL Profiles] ノード [!DNL Detailed Status] data workbench のインターフェイス。 詳しくは、 [!DNL Detailed Status] インターフェイスについては、 *Data Workbenchユーザーガイド*.
