---
description: Report Serverのステータスとレポートセットのステータスに関する情報です。
title: レポートのステータスの確認
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# レポートのステータスの確認{#reviewing-report-status}

Report Serverのステータスとレポートセットのステータスに関する情報です。

* [レポートサーバーのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [レポートセットのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## レポートサーバーの状態{#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推奨頻度：** 必要な場合のみ

[!DNL Report] サーバーのステータスに関するステータス情報を2分おきにdata workbenchサーバーに送信し [!DNL Report] ます。この情報は、[!DNL Detailed Status]インターフェイスの[!DNL Report Server Status]ノードの下で確認できます。

**ビジュアライ [!DNL Detailed Status] ゼーションを開くには**

1. data workbenchで、ワークスペース内で右クリックし、**[!UICONTROL Admin]**/**[!UICONTROL Servers]**&#x200B;をクリックします。

1. [!DNL Servers]インターフェイスで、[!DNL Report]コンピューターが接続するdata workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Detailed Status.]**」をクリックします

1. 「**[!UICONTROL Report Server Status]**」をクリックします。

複数の[!DNL Report]がdata workbenchサーバーに接続されている場合、各[!DNL Report Server]のエントリがStatusベクトルに表示されます。 2分の間隔は、[!DNL ReportServer.cfg]ファイルの[!DNL Reporting]ノードのStatus Interval（秒）パラメーターの値を指定することで上書きできます。

[!DNL ReportServer.cfg]ファイルについて詳しくは、[レポートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)を参照してください。 [!DNL Report]の設定について詳しくは、[レポートのインストール](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)を参照してください。

[!DNL Detailed Status]の詳細については、『*Data Workbenchユーザーガイド*』の「管理インターフェイス」という章を参照してください。

## レポートセットの状態{#section-8569b94266b74a1f85d2a85106a2aaef}

**推奨頻度：** 必要な場合のみ

[!DNL Report] 各レポートセットのステータス情報をData Workbenchサーバに送信します。レポートセットが生成されたときや配布された場所などの基本情報は、data workbenchのレポートセットの上に緑のテキストで表示されます。 [!DNL Report]サーバーは、レポートの実行中、現在のクエリの完了率を示すメッセージを2分ごとに出力します。 この2分間隔は、[!DNL ReportServer.cfg]ファイルの[!DNL Reporting]ノードのCompletion Message Interval（秒）パラメーターの値を指定することで上書きできます。

![](assets/report_status.png)

>[!NOTE]
>
>レポートの実行中にエラーが発生した場合は、そのレポートのサムネールの下に赤いテキストでエラーが示されます。 ワークスペースを右クリックすると、完全なエラーメッセージが表示されます。
