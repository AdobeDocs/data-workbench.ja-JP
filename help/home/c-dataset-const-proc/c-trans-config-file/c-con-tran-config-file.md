---
description: Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。
title: 変換設定ファイルに関する考慮事項
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 49%

---

# 変換設定ファイルに関する考慮事項{#considerations-for-the-transformation-configuration-file}

Transformation.cfg ファイルを編集する際に考慮すべき重要な情報について取り上げます。

* このファイルに含まれるいずれかのパラメーターを変更した場合、データの再変換が必要となります。
* データを再処理する場合は、Data Workbenchの[!DNL Processing Legend]で[!DNL Transformation Progress]パラメーターを確認できます。

   データの再処理や[!DNL Processing Legend,]について詳しくは、[再処理と再変換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)を参照してください。

* [!DNL CrossRows]、  [!DNL ODBCLookup]、  [!DNL Sessionize]、および変換 [!DNL AppendURI] は、ファイル内で定義されている場合にのみ機 [!DNL Transformation Dataset Configuration] 能します。これらの変換について詳しくは、[データ変換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)を参照してください。

   >[!NOTE]
   >
   >Adobeでは、データセット構築の変換段階で変換を定義する場合、1つ以上の[!DNL Transformation Dataset Include]ファイルを使用することをお勧めします。 詳しくは、[変換データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)を参照してください。

* 前述のパラメーターはいずれも [!DNL Transformation.cfg] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

   データセットプロファイルのデータセット構築プロセスの変換段階で発生したエラーは、Data Workbenchの[!DNL Detailed Status]インターフェイスの[!DNL Profiles]ノードに表示されます。 [!DNL Detailed Status]インターフェイスについて詳しくは、『*Data Workbenchユーザーガイド*』を参照してください。
