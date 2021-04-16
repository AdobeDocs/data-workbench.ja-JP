---
description: アラートを設定し、センサーのシステムステータスをチェックして、送信機が実行中かどうかを確認します。
title: データトランスミッターの実行状態の確認
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---

# データトランスミッターの実行状態の確認{#confirming-that-the-data-transmitter-is-running}

アラートを設定し、センサーのシステムステータスをチェックして、送信機が実行中かどうかを確認します。

**推奨頻度：5 ～ 10分** ごと

* [送信機プロセスが実行中であることを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Insightサーバーで管理アラートを設定します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [センサーのシステムステータスを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 送信機プロセスのチェック{#section-79806fa3b7034a8eaf571a66e24874d7}

送信機が実行されていることを確認する1つの方法は、[!DNL Sensor]インスタンスがインストールされている各Webサーバーで[!DNL Sensor]送信機プロセスが実行されていることを確認することです。 送信側のプロセスは、Webサーバーのプロセスのリストでは「txlogd」として表示されます。 このチェックは、システム監視ツールを使用して実行できます。

## Data Workbenchサーバーでの管理警告の設定{#section-d98e0f18b8fb45a78419fe75610a3b1e}

送信機が実行されていることを確認する別の方法は、[!DNL data workbench server]に自動管理アラートを設定することです。 管理アラートが設定されている場合、[!DNL data workbench server]は、設定済みで、以前に接続した[!DNL Sensor]から、[!DNL data workbench server’s] [!DNL Administrative Alerts.cfg]ファイルの[!DNL Sensor] Alert Timeout (min)パラメーターで指定された時間内にデータを受け取らないときに電子メールアラートを生成します。 管理アラートの設定について詳しくは、『*サーバー製品のインストールと管理に関するガイド*』を参照してください。

## センサーのシステムステータスの確認{#section-de9d7e359242487a9fbead4ed65aebbc}

しかし、送信機が動作していることを確認する別の方法は、Data Workbenchの[!DNL Servers Manager]を手動でチェックすることです。

**表示するには[!DNL Servers Manager]**

* Data Workbenchで、ワークスペース内で右クリックし、**[!UICONTROL Admin]**&#x200B;をクリックしてから、[!DNL Manage]の下の&#x200B;**[!UICONTROL Servers]**&#x200B;をクリックします。

[!DNL Sensor]のアイコンが緑色の場合は、送信機は動作中です。

[!DNL Servers Manager]の詳細については、『*Data Workbench[!DNL Sensor]ガイド*』の「管理インターフェイス」の章を参照してください。
