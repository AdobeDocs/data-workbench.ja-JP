---
description: レポートとアラートを生成する前に、Insightサーバーのアドレスと、レポート対象のプロファイルを識別するように、レポートサーバーを設定する必要があります。
title: Insight サーバーへの接続の設定
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 9%

---

# Insight サーバーへの接続の設定{#configuring-the-connection-to-the-insight-server}

レポートとアラートを生成する前に、Insightサーバーのアドレスと、レポート対象のプロファイルを識別するように、レポートサーバーを設定する必要があります。

>[!NOTE]
>
>以下の説明に従ってReport Serverを設定するまで、Report Serverを正常に実行できません。 プログラムと共にインストールされた未設定のファイルを使用してReport Serverを実行しようとすると、Report Serverはエラーのストリームを生成します。

**Report Serverを設定するには**

1. Windowsエクスプローラで、Report Serverをインストールしたディレクトリに移動します。
1. [!DNL ReportServer.cfg]ファイルをメモ帳で開き、必要に応じて変更します。

   次のサンプル[!DNL Report Server.cfg]には、デフォルトで[!DNL Report Server.cfg]ファイルに含まれているパラメーターのみが含まれています（必要なパラメーター設定が強調表示されています）。 プロキシサーバー経由でAdobeライセンスサーバーに連絡する場合は、Licensingベクトルとそのパラメーターを追加する必要があります。 詳しくは、[Report Server.cfg parameters](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06)を参照してください。

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
