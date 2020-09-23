---
description: 監査ログファイルでは、Insightサーバーとの接続および接続解除の試行をすべて追跡します。各接続は、デフォルトで、Insightサーバーのインストールディレクトリ内のAuditフォルダーにある<YYYYMMDD>-access.txtファイルに記録されます。
solution: Analytics
title: 監査ログの監視
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# 監査ログの監視{#monitoring-audit-logs}

監査ログファイルは、Insightサーバーとの接続および接続解除の試行をすべて追跡します。各接続は、デフォルトで、Insightサーバーのインストールディレクトリ内のAuditフォルダーにある `<YYYYMMDD>-access.txt` ファイルに記録されます。

**推奨頻度：** 毎日、またはトラブルシューティングに必要な時

への接続に関する問題をトラブルシューティングする際に、監査ログが非常に役立つ場合があり [!DNL Insight Server]ます。 これらのログは、自動管理ツールを使用して監視するか、 [!DNL access.txt] ファイルを直接表示することで監視できます。

**access.txtファイルを[!DNL Server Files Manager]**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. アクティブなアイコンを右クリックし、 [!DNL Insight Server] をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Audit]** to view its contents.
1. 目的のファイルの横にある *サーバー名* 列のチェックマークを右クリックし、をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 列のファイル名の横にチェックマークが表示され [!DNL Temp] ます。
1. 列の新しいチェックマークを右クリックし、 [!DNL Temp] /をクリックし **[!UICONTROL Open]** ま **[!UICONTROL in Notepad]**&#x200B;す。 監査ログは、Microsoft Windowsの新しいメモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/cfg_accesscontrol_accessFile.png)

