---
description: アラートを設定し、センサーのシステムステータスを確認して、送信機が動作しているかどうかを確認します。
solution: Insight
title: データ送信機の実行の確認
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# データ送信機の実行の確認{#confirming-that-the-data-transmitter-is-running}

アラートを設定し、センサーのシステムステータスを確認して、送信機が動作しているかどうかを確認します。

**推奨頻度：** 5 ～ 10分ごと

* [送信機プロセスが実行中であることを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7)
* [Insightサーバーで管理アラートを設定します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e)
* [センサーのシステムステータスを確認します。](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## 送信機プロセスの確認 {#section-79806fa3b7034a8eaf571a66e24874d7}

送信機が実行されていることを確認する1つの方法は、インスタンスがインストールされ [!DNL Sensor] ている各Webサーバー上で送信機プロセスが実行されてい [!DNL Sensor] ることを確認することです。 送信プロセスは、Webサーバーのプロセスのリストに「txlogd」として表示されます。 このチェックは、システム監視ツールを使用して実行できます。

## Data Workbenchサーバーでの管理アラートの設定 {#section-d98e0f18b8fb45a78419fe75610a3b1e}

送信機が実行されていることを確認する別の方法は、で自動管理アラートを設定することで [!DNL data workbench server]す。 管理アラートが設定されている場合、 [!DNL data workbench server] は、設定済みで、以前に接続されたデータをファイル内の [!DNL Sensor] Alert Timeout (min)パラメーターで指定された時間枠内に受信しなかった場合に、電子メールアラートを生成し [!DNL Sensor][!DNL data workbench server’s][!DNL Administrative Alerts.cfg] ます。 For more information about setting up administrative alerts, see the *Server Products Installation and Administration Guide*.

## センサーのシステムステータスの確認 {#section-de9d7e359242487a9fbead4ed65aebbc}

また、送信機が実行されていることを確認する別の方法は、Data Workbenchで手動でチェッ [!DNL Servers Manager] クすることです。

**を表示するには[!DNL Servers Manager]**

* Data Workbenchで、ワークスペース内で右クリックし、をクリッ **[!UICONTROL Admin]**&#x200B;クしてから、の下のをク [!DNL Manage]リックしま **[!UICONTROL Servers]**&#x200B;す。

のアイコンが緑色の場 [!DNL Sensor] 合は、送信機が動作しています。

For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench[!DNL Sensor]Guide*.
