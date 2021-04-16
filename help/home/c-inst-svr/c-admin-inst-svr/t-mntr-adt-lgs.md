---
description: 監査ログファイルでは、Insightサーバーとの接続および接続解除の試行をすべて追跡します。各接続は、デフォルトで、Insightサーバーのインストールディレクトリ内のAuditフォルダーにある<YYYYMMDD>-access.txtファイルに記録されます。
title: 監査ログの監視
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 監査ログの監視{#monitoring-audit-logs}

監査ログファイルは、Insightサーバーとの接続および接続解除の試行をすべて追跡します。各接続は、デフォルトで、Insightサーバーのインストールディレクトリ内のAuditフォルダーにある`<YYYYMMDD>-access.txt`ファイルに記録されます。

**推奨頻度：** 毎日、またはトラブルシューティングに必要な時

[!DNL Insight Server]への接続に関する問題をトラブルシューティングする際に、監査ログが非常に役立ちます。 これらのログは、自動管理ツールを使用して監視するか、[!DNL access.txt]ファイルを直接表示して監視できます。

**access.txtファイルを[!DNL Server Files Manager]**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. アクティブな[!DNL Insight Server]のアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。
1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Audit]**&#x200B;をクリックして、内容を表示します。
1. 目的のファイルの横の&#x200B;*server name*&#x200B;列のチェックマークを右クリックし、「**[!UICONTROL Make Local]**」をクリックします。 [!DNL Temp]列のファイル名の横にチェックマークが表示されます。
1. [!DNL Temp]列の新しいチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。 監査ログは、Microsoft Windowsの新しいメモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/cfg_accesscontrol_accessFile.png)
