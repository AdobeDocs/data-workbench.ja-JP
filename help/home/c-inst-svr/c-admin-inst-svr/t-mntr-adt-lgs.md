---
description: 監査ログファイルは、Insight サーバーへの接続および Insight サーバーからの接続解除が試行されたすべてを追跡し、それぞれが <yyyymmdd>デフォルトでは、Insight Server インストールディレクトリ内の Audit フォルダーにある —access.txt ファイル。
title: 監査ログの監視
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 監査ログの監視{#monitoring-audit-logs}

{{eol}}

監査ログファイルは、Insight サーバーへの接続および Insight サーバーからの接続解除が試行されたすべてを追跡し、それぞれが `<YYYYMMDD>-access.txt` デフォルトで、Insight サーバーのインストールディレクトリ内の Audit フォルダーにあるファイル。

**推奨頻度：** 毎日、またはトラブルシューティングの必要に応じて

監査ログは、 [!DNL Insight Server]. これらのログは、自動管理ツールを使用して、または [!DNL access.txt] ファイルを直接参照してください。

**access.txt ファイルを[!DNL Server Files Manager]**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. アクティブな [!DNL Insight Server] をクリックし、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Audit]** をクリックして、その内容を表示します。
1. チェックマーク ( *サーバー名* 列をクリックし、 **[!UICONTROL Make Local]**. ファイル名の横に、 [!DNL Temp] 列。
1. 新しいチェックマークを右クリックし、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 監査ログが新しいMicrosoft Windows メモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/cfg_accesscontrol_accessFile.png)
