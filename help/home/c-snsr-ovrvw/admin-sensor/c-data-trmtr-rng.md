---
description: アラートを設定し、センサーのシステムステータスをチェックして、送信機が実行中かどうかを確認します。
solution: Analytics
title: データトランスミッターの実行状態の確認
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 5%

---


# データトランスミッターの実行状態の確認{#confirming-that-the-data-transmitter-is-running}

アラートを設定し、センサーのシステムステータスをチェックして、送信機が実行中かどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [送信機プロセスが実行中であることを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Insightサーバーで管理アラートを設定します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [センサーのシステムステータスを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 送信機プロセスのチェック {#section-79806fa3b7034a8eaf571a66e24874d7}

送信機が実行されていることを確認する1つの方法は、インスタンスがインストールされている各Webサーバーで [!DNL Sensor] 送信機プロセスが実行されていることを確認することで [!DNL Sensor] す。 送信側のプロセスは、Webサーバーのプロセスのリストでは「txlogd」として表示されます。 このチェックは、システム監視ツールを使用して実行できます。

## Data Workbenchサーバーでの管理アラートの設定 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

送信機が実行されていることを確認する別の方法は、で自動管理アラートを設定すること [!DNL data workbench server]です。 管理アラートが設定されている場合、設定済みで、以前に接続したアラートから、 [!DNL data workbench server] ファイルのAlert Timeout(min)パラメーターで指定された時間枠内にデータを受け取っていないときに、電子メールアラートが [!DNL Sensor][!DNL Sensor][!DNL data workbench server’s][!DNL Administrative Alerts.cfg] 生成されます。 For more information about setting up administrative alerts, see the *Server Products Installation and Administration Guide*.

## センサーのシステムステータスの確認 {#section-de9d7e359242487a9fbead4ed65aebbc}

また、トランスミッタが実行されていることを確認する別の方法として、インData Workbenchを手動でチェックす [!DNL Servers Manager] る方法があります。

**表示するには[!DNL Servers Manager]**

* Data Workbenchで、ワークスペース内で右クリックし、をクリックし **[!UICONTROL Admin]**&#x200B;てから、の下のをクリック [!DNL Manage]し **[!UICONTROL Servers]**&#x200B;ます。

のアイコンが緑色の場合 [!DNL Sensor] は、トランスミッターが実行中です。

For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench[!DNL Sensor]Guide*.
