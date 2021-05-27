---
description: レポートサーバーのステータスとレポートセットのステータスに関する情報です。
title: レポートのステータスの確認
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# レポートのステータスの確認{#reviewing-report-status}

レポートサーバーのステータスとレポートセットのステータスに関する情報です。

* [レポートサーバーのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [レポートセットのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## レポートサーバーのステータス{#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推奨頻度：** 必要な場合のみ

[!DNL Report] は、サーバーのステータスに関するステータス情報を2分ごとにdata workbenchサーバーに送信 [!DNL Report] します。この情報は、[!DNL Detailed Status]インターフェイスの[!DNL Report Server Status]ノードで確認できます。

**ビジュアライゼーションを開く [!DNL Detailed Status] には**

1. Data Workbenchで、ワークスペース内を右クリックし、**[!UICONTROL Admin]** / **[!UICONTROL Servers]**&#x200B;をクリックします。

1. [!DNL Servers]インターフェイスで、[!DNL Report]マシンが接続するData Workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Detailed Status.]**」をクリックします

1. 「**[!UICONTROL Report Server Status]**」をクリックします。

複数の[!DNL Report]がData Workbenchサーバーに接続されている場合は、 Statusベクトル内の各[!DNL Report Server]に対してエントリが表示されます。 2分間隔は、[!DNL ReportServer.cfg]ファイルの[!DNL Reporting]ノードのStatus Interval (seconds)パラメーターの値を指定することで上書きできます。

[!DNL ReportServer.cfg]ファイルについて詳しくは、[レポートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)を参照してください。 [!DNL Report]の設定について詳しくは、[レポートのインストール](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91)を参照してください。

[!DNL Detailed Status]の詳細については、『*Data Workbenchユーザーガイド*』の「管理インターフェイス」の章を参照してください。

## レポートセットのステータス{#section-8569b94266b74a1f85d2a85106a2aaef}

**推奨頻度：** 必要な場合のみ

[!DNL Report] は、各レポートセットのステータス情報をData Workbench・サーバに送信する。レポートセットの生成時や配布先などの基本情報は、Data Workbenchのレポートセットの上に緑色のテキストで表示されます。 [!DNL Report]サーバーは、レポートの実行中、現在のクエリの完了率を示すメッセージを2分ごとに出力します。 この2分間隔は、[!DNL ReportServer.cfg]ファイルの[!DNL Reporting]ノードのCompletion Message Interval (seconds)パラメーターの値を指定することで上書きできます。

![](assets/report_status.png)

>[!NOTE]
>
>レポートの実行中にエラーが発生した場合は、そのレポートのサムネールの下に赤いテキストが表示されます。 ワークスペースを右クリックすると、完全なエラーメッセージを表示できます。
