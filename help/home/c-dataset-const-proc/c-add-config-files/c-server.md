---
description: Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。
solution: Analytics
title: Server.cfg
topic: Data workbench
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server.cfg{#server-cfg}

Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。

デフォルト値は 250e6 です。Instructions for opening and saving the [!DNL Server.cfg] file are the same as those for [!DNL Log Processing Mode.cfg]. See [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>このファイルのパラメーターはシステムのパフォーマンスに影響するので、変更を加える前にアドビにお問い合わせください。

さらに、[!DNL Insight.cfg] ファイルで Maximum Sample Size パラメーターを設定することにより、Data Workbench サーバーに接続する Data Workbench コンピューターのデータキャッシュのサイズを制限することができます。詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。
