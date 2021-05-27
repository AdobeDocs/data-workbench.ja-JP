---
description: アラートを設定したり、センサーのシステムステータスを確認したりして、トランスミッターが動作しているかどうかを確認します。
title: データトランスミッターの実行状態の確認
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# データトランスミッターの実行状態の確認{#confirming-that-the-data-transmitter-is-running}

アラートを設定したり、センサーのシステムステータスを確認したりして、トランスミッターが動作しているかどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [トランスミッタープロセスが実行中であることを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Insightサーバーで管理アラートを設定します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [センサーのシステムステータスを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## トランスミッタープロセス{#section-79806fa3b7034a8eaf571a66e24874d7}の確認

トランスミッターが実行されていることを確認する1つの方法は、[!DNL Sensor]インスタンスがインストールされている各Webサーバーで[!DNL Sensor]トランスミッタープロセスが実行されていることを確認することです。 トランスミッタープロセスは、Webサーバーのプロセスのリストに「txlogd」と表示されます。 このチェックは、システム監視ツールを使用して実行できます。

## Data Workbench・サーバ{#section-d98e0f18b8fb45a78419fe75610a3b1e}での管理アラートの設定

トランスミッターが実行中であることを確認するもう1つの方法は、[!DNL data workbench server]で自動管理アラートを設定することです。 管理アラートが設定されている場合、 [!DNL data workbench server]は、 [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]ファイルの[!DNL Sensor] Alert Timeout (min)パラメーターで指定された時間枠内に、設定済みで以前に接続された[!DNL Sensor]からデータを受信しないと、電子メールアラートを生成します。 管理アラートの設定について詳しくは、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

## センサーのシステムステータスの確認{#section-de9d7e359242487a9fbead4ed65aebbc}

しかし、トランスミッターが実行中であることを確認するもう1つの方法は、Data Workbenchの[!DNL Servers Manager]を手動で確認することです。

**を表示するには、[!DNL Servers Manager]**

* Data Workbenchで、ワークスペース内を右クリックし、「**[!UICONTROL Admin]**」をクリックし、「[!DNL Manage]」で「**[!UICONTROL Servers]**」をクリックします。

[!DNL Sensor]のアイコンが緑色の場合、トランスミッターは実行中です。

[!DNL Servers Manager]の詳細については、『*Data Workbench[!DNL Sensor]ガイド*』の「管理インターフェイス」の章を参照してください。
