---
description: レポートサーバーのステータスとレポートセットのステータスに関する情報です。
title: レポートのステータスの確認
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# レポートのステータスの確認{#reviewing-report-status}

{{eol}}

レポートサーバーのステータスとレポートセットのステータスに関する情報です。

* [レポートサーバーのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [レポートセットのステータス](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## レポートサーバーのステータス {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**推奨頻度：** 必要な場合のみ

[!DNL Report] は、 [!DNL Report] サーバー。 この情報は、 [!DNL Report Server Status] ノードを [!DNL Detailed Status] インターフェイス。

**次の手順で [!DNL Detailed Status] 視覚化**

1. Data Workbench で、ワークスペース内を右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. 内 [!DNL Servers] インターフェイスで、 [!DNL Report] マシンがに接続し、 **[!UICONTROL Detailed Status.]**

1. 「**[!UICONTROL Report Server Status]**」をクリックします。

複数の [!DNL Report] が data workbench サーバーに接続されている場合は、各 [!DNL Report Server] 」と入力します。 2 分間隔は、 [!DNL Reporting] ノード [!DNL ReportServer.cfg] ファイル。

詳しくは、 [!DNL ReportServer.cfg] ファイル： [レポートセットの設定](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). 設定に関する情報 [!DNL Report]を参照してください。 [レポートのインストール](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

詳しくは、 [!DNL Detailed Status]詳しくは、 *Data Workbenchユーザーガイド*.

## レポートセットのステータス {#section-8569b94266b74a1f85d2a85106a2aaef}

**推奨頻度：** 必要な場合のみ

[!DNL Report] は、各レポートセットのステータス情報をData Workbench・サーバに送信します。 レポートセットの生成時や配布先などの基本情報は、Data Workbench のレポートセットの上に緑色のテキストで表示されます。 レポートの実行中、 [!DNL Report] サーバーは、現在のクエリの完了率を示すメッセージを 2 分ごとに出力します。 この 2 分間隔は、 [!DNL Reporting] ノード [!DNL ReportServer.cfg] ファイル。

![](assets/report_status.png)

>[!NOTE]
>
>レポートの実行中にエラーが発生した場合は、そのレポートのサムネールの下に赤いテキストでエラーが表示されます。 ワークスペースを右クリックすると、完全なエラーメッセージが表示されます。
