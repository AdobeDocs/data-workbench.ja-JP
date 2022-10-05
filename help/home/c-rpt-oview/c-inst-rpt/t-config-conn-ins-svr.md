---
description: レポートとアラートを生成する前に、レポートサーバーを設定して、Insight サーバーのアドレスと、レポート対象のプロファイルを特定する必要があります。
title: Insight サーバーへの接続の設定
uuid: 2018b67e-90a6-41d7-b628-4b463869df6e
exl-id: a398a665-fe09-448a-977c-b0f9de4add09
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 9%

---

# Insight サーバーへの接続の設定{#configuring-the-connection-to-the-insight-server}

{{eol}}

レポートとアラートを生成する前に、レポートサーバーを設定して、Insight サーバーのアドレスと、レポート対象のプロファイルを特定する必要があります。

>[!NOTE]
>
>以下の説明に従ってレポートサーバーを設定するまでは、レポートサーバーを正常に実行できません。 プログラムと共にインストールされた未構成のファイルでレポートサーバを実行しようとすると、レポートサーバはエラーのストリームを生成します。

**レポートサーバーを設定するには**

1. Windows エクスプローラで、Report Server をインストールしたディレクトリに移動します。
1. を開きます。 [!DNL ReportServer.cfg] ファイルをメモ帳に保存し、必要に応じてファイルを変更します。

   次のサンプル [!DNL Report Server.cfg] には、 [!DNL Report Server.cfg] ファイル（デフォルト）（およびは必須のパラメータ設定をハイライト表示） プロキシサーバを通じてAdobeライセンスサーバに接続する場合は、Licensing ベクトルとそのパラメータを追加する必要があります。 詳しくは、 [Report Server.cfg のパラメーター](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-svr-param.md#concept-53359b328fd140d593c3f2fc0031be06) を参照してください。

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
