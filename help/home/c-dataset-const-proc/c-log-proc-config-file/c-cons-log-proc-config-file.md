---
description: Log Processing.cfg ファイルを編集する際に考慮すべき概念について取り上げます。
solution: Analytics
title: ログ処理設定ファイルに関する考慮事項
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ログ処理設定ファイルに関する考慮事項{#considerations-for-the-log-processing-configuration-file}

Log Processing.cfg ファイルを編集する際に考慮すべき概念について取り上げます。

* データセットのソースを定義した後でデータファイルを別のディレクトリに移動することは避けてください。ディレクトリに追加されるファイルは、Data Workbench サーバーが Sensor からデータを受け取った結果として新たに作成されたファイルのみであることが必要です。
* このファイルに含まれるいずれかのパラメーターを変更した場合、全データの再処理が必要となります。再処理を行うためには、[!DNL Log Processing Mode.cfg] ファイルの Pause パラメーターが false に設定されている必要があります（このパラメーターの値はデフォルトで false になっているので、通常、変更は不要です）。このファイルについて詳し [!DNL Log Processing Mode.cfg] くは、「追加の設定フ [ァイル」を参照してくださ](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)い。

* If you reprocess the data, you can check the Log Processing Progress parameter in data workbench&#39;s [!DNL Processing Legend].

   データの再処理について詳しくは、再処理と再変換 [を参照してください](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。 処理の凡 [例を参照](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)。

* [!DNL Log Processing.cfg] ファイルは、複数のデータセットプロファイル間で共有できます。[!DNL Log Processing.cfg] ファイルで定義されている変換は、この設定ファイルを共有するすべてのデータセットプロファイルに適用されます。

   >[!NOTE]
   >
   >Adobe recommends defining transformations for the log processing in one or more log processing [!DNL dataset include] files. 詳しくは、ログ処理データセッ [トインクルードファイルを参照してくださ](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)い。

* 前述のパラメーターはいずれも [!DNL Log Processing.cfg] ファイルをメモ帳で開いて編集することによって追加することができます。編集後、保存した内容は、Data Workbench でファイルを開き直すと表示されます。新しいパラメーターを追加する際は、（Tab キーではなく）スペースキーで空白を 2 つ追加し、前の見出しレベルの右にインデントします。

   Any errors that occur during the log processing phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

