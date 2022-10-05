---
description: アラートを設定し、センサーのシステムステータスを確認して、トランスミッターが動作しているかどうかを確認します。
title: データトランスミッターの実行状態の確認
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# データトランスミッターの実行状態の確認{#confirming-that-the-data-transmitter-is-running}

{{eol}}

アラートを設定し、センサーのシステムステータスを確認して、トランスミッターが動作しているかどうかを確認します。

**推奨頻度：** 5 ～ 10 分ごと

* [トランスミッタープロセスが実行中であることを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Insight サーバーで管理アラートを設定します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [センサーのシステムステータスを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## トランスミッタープロセスの確認 {#section-79806fa3b7034a8eaf571a66e24874d7}

トランスミッターが実行されていることを確認する方法の 1 つは、 [!DNL Sensor] トランスミッタープロセスは、 [!DNL Sensor] インスタンスがインストールされている。 トランスミッタープロセスは、Web サーバーのプロセスのリストに「txlogd」と表示されます。 このチェックは、システム監視ツールを使用して実行できます。

## Data Workbench・サーバでの管理アラートの設定 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

トランスミッターが実行中であることを確認するもう 1 つの方法は、 [!DNL data workbench server]. 管理アラートが設定されている場合、 [!DNL data workbench server] 設定済みで以前に接続されたからデータを受信しなかった場合に電子メールアラートを生成します [!DNL Sensor] が [!DNL Sensor] のアラートタイムアウト（分）パラメーター [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] ファイル。 管理アラートの設定の詳細については、 *サーバー製品のインストールおよび管理ガイド*.

## センサーのシステムステータスの確認 {#section-de9d7e359242487a9fbead4ed65aebbc}

トランスミッターが動作していることを確認する別の方法は、 [!DNL Servers Manager] Data Workbench

**次の手順で[!DNL Servers Manager]**

* Data Workbench内で右クリックし、 **[!UICONTROL Admin]**&#x200B;次に、 [!DNL Manage]をクリックし、 **[!UICONTROL Servers]**.

アイコンが [!DNL Sensor] が緑の場合は、トランスミッターが動作しています。

詳しくは、 [!DNL Servers Manager]詳しくは、 *Data Workbench [!DNL Sensor] ガイド*.
