---
description: レポートとアラートを生成する前に、Insightサーバーのアドレスを指定し、レポート対象のプロファイルを指定するようにレポートサーバーを設定する必要があります。
solution: Analytics
title: Insightサーバーへの接続の設定
topic: Data workbench
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuring the Connection to the Insight Server{#configuring-the-connection-to-the-insight-server}

レポートとアラートを生成する前に、Insightサーバーのアドレスを指定し、レポート対象のプロファイルを指定するようにレポートサーバーを設定する必要があります。

>[!NOTE]
>
>以下の説明に従ってReport Serverを設定するまで、Report Serverを正常に実行することはできません。 プログラムと共にインストールされた設定されていないファイルでReport Serverを実行しようとすると、Report Serverはエラーのストリームを生成します。

**Report Serverを設定するには**

1. Windowsエクスプローラで、Report Serverをインストールしたディレクトリに移動します。
1. メモ帳でフ [!DNL ReportServer.cfg] ァイルを開き、必要に応じてファイルを変更します。

   次のサンプルには、デ [!DNL Report Server.cfg] フォルトでファイルに含まれてい [!DNL Report Server.cfg] るパラメータのみが含まれています（必要なパラメータ設定がハイライト表示されています）。 プロキシサーバーを通じてAdobe License Serverに接続する場合は、Licensingベクトルとそのパラメーターを追加する必要があります。 詳しく [は、Report Server.cfgのパラメーター](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) （英語のみ）を参照してください。

   ```
   Fonts = vector: 0 items
   Gamma = float: 1.6
   Network Location = string: NetworkLocationName
   Servers = vector: 1 items
     0 = serverInfo:
       Address = string: ServerIPAddress
       Name = string: 
       Port = int: 443
       Proxy Address = string:
       Proxy Password = string:
       Proxy Port = int: 8080
       Proxy User Name = string:
       SSL Client Certificate = string: ReportCertFileName.pem
       SSL Server Common Name = string: ServerCommonName
       Use SSL = bool: true
   Result Memory Limit (KB) = double: 100000
   Maximum Slice Size = int: 30
   Use OpenGL Hardware Rendering = bool: true
   Reporting = :
     Profiles = vector: 1 items
       0 = ReportProfile:
         Server = string: ServerCommonName
         Profile = string: ProfileName
     Update Interval (minutes) = int: 10
     Completion Message Interval (seconds) = int: 600
     Status interval (seconds) = int: 600
     SMTP Server for Errors = string: SMTPServerHostName
     SMTP Server for Errors Username = string: SMTPServerUsername
     SMTP Server for Errors Password = string: SMTPServerPassword
     SMTP Server for Errors Send From = string: SenderAddress
     SMTP Server for Errors Send To = string: RecipientAddresses
   ```

1. ファイルを保存して閉じます。
