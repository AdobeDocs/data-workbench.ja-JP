---
description: Log Processing.cfg ファイルを編集する際に考慮すべき概念について取り上げます。
title: ログ処理設定ファイルに関する考慮事項
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 66%

---

# ログ処理設定ファイルに関する考慮事項{#considerations-for-the-log-processing-configuration-file}

{{eol}}

Log Processing.cfg ファイルを編集する際に考慮すべき概念について取り上げます。

* データセットのソースを定義した後でデータファイルを別のディレクトリに移動することは避けてください。ディレクトリに追加されるファイルは、Data Workbench サーバーが Sensor からデータを受け取った結果として新たに作成されたファイルのみであることが必要です。
* このファイルに含まれるいずれかのパラメーターを変更した場合、全データの再処理が必要となります。再処理を行うためには、[!DNL Log Processing Mode.cfg] ファイルの Pause パラメーターが false に設定されている必要があります（このパラメーターの値はデフォルトで false になっているので、通常、変更は不要です）。詳しくは、 [!DNL Log Processing Mode.cfg] ファイル： [追加の設定ファイル](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* データを再処理する場合は、Data Workbench の [!DNL Processing Legend].

   データの再処理について詳しくは、 [再処理と再変換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md). 詳しくは、 [処理の凡例](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828).

* [!DNL Log Processing.cfg] ファイルは、複数のデータセットプロファイル間で共有できます。[!DNL Log Processing.cfg] ファイルで定義されている変換は、この設定ファイルを共有するすべてのデータセットプロファイルに適用されます。

   >[!NOTE]
   >
   >Adobeでは、ログ処理の変換を 1 つ以上のログ処理に定義することをお勧めします [!DNL dataset include] ファイル。 詳しくは、 [ログ処理データセットインクルードファイル](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* 前述のパラメーターはいずれも [!DNL Log Processing.cfg] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

   データセットプロファイルのデータセット構築プロセスのログ処理段階で発生したエラーは、 [!DNL Profiles] ノード [!DNL Detailed Status] data workbench のインターフェイス。 詳しくは、 [!DNL Detailed Status] インターフェイスについては、 *Data Workbenchユーザーガイド*.
