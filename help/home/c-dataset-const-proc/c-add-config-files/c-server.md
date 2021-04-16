---
description: Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。
title: Server.cfg
uuid: 7e789133-09fc-442d-b643-cca8620f4a97
exl-id: fb7667f6-4061-4bde-8a48-6489b24e0411
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 72%

---

# Server.cfg{#server-cfg}

Data Workbench で使用するデータのキャッシュサイズ（バイト単位）は、Server.cfg ファイルの Sample Bytes パラメーターで指定します。

デフォルト値は 250e6 です。[!DNL Server.cfg]ファイルを開いて保存する手順は、[!DNL Log Processing Mode.cfg]の場合と同じです。 [Log Processing Mode.cfg](../../../home/c-dataset-const-proc/c-add-config-files/t-log-proc-mode.md#task-e530907cb34f488182afe625e6d9e44a)を参照してください。

>[!NOTE]
>
>このファイルのパラメーターはシステムのパフォーマンスに影響を与えるので、変更を加える前にAdobeにお問い合わせください。

さらに、[!DNL Insight.cfg] ファイルで Maximum Sample Size パラメーターを設定することにより、Data Workbench サーバーに接続する Data Workbench コンピューターのデータキャッシュのサイズを制限することができます。詳しくは、『*Data Workbench ユーザーガイド*』を参照してください。
