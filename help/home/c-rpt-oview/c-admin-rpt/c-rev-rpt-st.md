---
description: レポートサーバーのステータスとレポートセットのステータスに関する情報です。
solution: Analytics
title: レポート・ステータスの確認
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポート・ステータスの確認{#reviewing-report-status}

レポートサーバーのステータスとレポートセットのステータスに関する情報です。

* [レポートサーバーのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [レポートセットのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## レポートサーバーのステータス {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推奨頻度：** 必要な場合のみ

[!DNL Report] サーバーのステータスに関するステータス情報を2分ごとにData Workbenchサーバーに送信し [!DNL Report] ます。 この情報は、インターフェイスのノード [!DNL Report Server Status] の下に表示さ [!DNL Detailed Status] れます。

**ビジュアライゼーションを開く[!DNL Detailed Status]には**

1. Data Workbenchで、ワークスペース内で右クリックし、/をクリッ **[!UICONTROL Admin]** クしま **[!UICONTROL Servers]**&#x200B;す。

1. インターフ [!DNL Servers] ェイスで、コンピューターが接続するData Workbenchサーバーのアイコンを右ク [!DNL Report] リックし、 **[!UICONTROL Detailed Status.]**

1. クリック **[!UICONTROL Report Server Status]**.

複数のエントリがData Workbench [!DNL Report] サーバーに接続されている場合、各エントリのStatusベクトル [!DNL Report Server] が表示されます。 2分間隔は、ファイルのノードのStatus Interval（秒）パラメーターで値を指定することで上書き [!DNL Reporting] でき [!DNL ReportServer.cfg] ます。

このファイルについて詳し [!DNL ReportServer.cfg] くは、「レポ [ートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)」を参照。 設定の詳細については、「レポートのイ [!DNL Report]ンストール」 [を参照してくださ](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)い。

For more information about [!DNL Detailed Status], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

## レポートセットのステータス {#section-8569b94266b74a1f85d2a85106a2aaef}

**推奨頻度：** 必要な場合のみ

[!DNL Report] 各レポートセットのステータス情報をData Workbenchサーバーに送信します。 レポートセットの生成日時や配布先などの基本情報は、Data Workbenchのレポートセットの上に緑のテキストで表示されます。 レポートの実行中、 [!DNL Report] Serverは、現在のクエリの完了率を示すメッセージを2分ごとに出力します。 この2分間隔は、ファイルのノードのCompletion Message Interval（秒）パラメーターで値を指定することで上書き [!DNL Reporting] でき [!DNL ReportServer.cfg] ます。

![](assets/report_status.png)

>[!NOTE]
>
>レポートの実行中にエラーが発生した場合は、そのレポートのサムネールの下に赤いテキストでエラーが示されます。 ワークスペースを右クリックして、完全なエラーメッセージを表示できます。

