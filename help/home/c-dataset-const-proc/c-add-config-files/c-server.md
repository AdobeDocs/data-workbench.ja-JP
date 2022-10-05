---
description: Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 72%

---

# Server.cfg{#server-cfg}

{{eol}}

Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。

デフォルト値は 250e6 です。を開いて保存する手順 [!DNL Server.cfg] ファイルは [!DNL Log Processing Mode.cfg]. 詳しくは、 [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a).

>[!NOTE]
>
>このファイルのパラメータはシステムのパフォーマンスに影響を与えるので、変更を加える前にAdobeにお問い合わせください。

さらに、[!DNL Insight.cfg] ファイルで Maximum Sample Size パラメーターを設定することにより、Data Workbench サーバーに接続する Data Workbench コンピューターのデータキャッシュのサイズを制限することができます。詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。
