---
description: 監査ログファイルは、Insightサーバーとの接続およびInsightサーバーとの接続解除の試行をすべて追跡します。各接続は、Insightサーバーのインストールディレクトリ内のAuditフォルダーにある<YYYYMMDD>-access.txtファイルにデフォルトで記録されます。
solution: Insight
title: 監査ログの監視
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 監査ログの監視{#monitoring-audit-logs}

監査ログファイルは、Insightサーバーとの接続およびInsightサーバーとの接続解除の試行をすべて追跡します。各接続は、Insightサーバーのインストールディレクトリ内のAuditフォルダーにあるデフォルトのファイルに `<YYYYMMDD>-access.txt` 記録されます。

**推奨頻度：** 毎日、またはトラブルシューティングに必要な時

に接続する際の問題をトラブルシューティングする際に、監査ログが非常に役立ちま [!DNL Insight Server]す。 これらのログは、自動管理ツールを使用して監視するか、ファイルを直接表示するこ [!DNL access.txt] とで監視できます。

**access.txtファイルを[!DNL Server Files Manager]**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. アクティブなアイコンを右クリックし、を [!DNL Insight Server] クリックしま **[!UICONTROL Server Files]**&#x200B;す。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Audit]** to view its contents.
1. 目的のファイルの横にあるサーバー名 *列のチェック* マークを右クリックし、をクリックしま **[!UICONTROL Make Local]**&#x200B;す。 列内のファイル名の横にチェックマークが表示され [!DNL Temp] ます。
1. 列の新しいチェックマークを右クリックし、/ [!DNL Temp] をクリッ **[!UICONTROL Open]** クしま **[!UICONTROL in Notepad]**&#x200B;す。 監査ログは、Microsoft Windowsの新しいメモ帳ウィンドウに表示されます。

   ![ステップ情報](assets/cfg_accesscontrol_accessFile.png)

