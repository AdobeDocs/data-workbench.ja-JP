---
description: Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。
title: レポートサーバーのアップグレードとアンインストール
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# レポートサーバーのアップグレードとアンインストール{#upgrading-and-uninstalling-report-server}

Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。

* [レポートのアップグレード](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [レポートのアンインストール](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## レポートサーバー{#section-95fea4bddad74616a8aea450dcdb2282}のアップグレード

[!DNL Report Server] 5.4にアップグレードする場合は、手順に従って[!DNL Report Server]ソフトウェアをアップグレードできます。 [!DNL Report Server] 3.6以前を使用している場合は、アップグレードに関してAdobeに問い合わせてください。

[!DNL Report Server] 5.4をアップグレードするには、Data Workbenchを使用して、[!DNL Report Server]の接続先のData Workbenchサーバーにアップグレードファイルをコピーします。 その後、[!DNL Report]サーバーインスタンスは、サーバーに接続してプロファイルを読み込む際に、自動的にアップグレードされます。

>[!NOTE]
>
>[!DNL Report Server]をアップグレードする前に、Data Workbenchサーバーソフトウェアと、Data Workbenchサーバー上で実行されているプロファイルが正しくアップグレードされていることを確認してください。 詳しくは、Adobe Consulting Services にお問い合わせください。

次の手順を実行するには、まず[!DNL Report Server]のアップグレードファイルを入手する必要があります。

**5.4以降のバ [!DNL Report Server] ージョンにアップグレードするには**

1. [!DNL E:\Portal]の下にあるすべてのファイルのバックアップを作成し、このディレクトリ内にあるすべてのファイルとフォルダを削除します。
1. 新しいビルドの内容を[!DNL E:\Portal]にコピーします。
1. 前の節の手順に従って、[!DNL global.asa]、[!DNL email.asp]、および[!DNL TopNavigation.xml]を変更します。

1. バックアップから[!DNL users.mdb]をコピーします。

   >[!NOTE]
   >
   >.png出力を含むレポートを以前に生成していない場合は、個々のレポートフォルダーに移動し、[!DNL reports.xml]を変更してpngのレポート形式を含める必要があります。 そうしないと、500エラーが発生する場合があります。 元の[!DNL reports.xml]は次のようになります。

   ```
      <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

   次のように変更する必要があります。

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <REPORTS>
    <REPORT format="xls">
     <NAME>Dashboard</NAME>
     <PATH>Dashboard.xls</PATH>
     <WEB_PATH>Dashboard.xls</WEB_PATH>
    </REPORT>
    <REPORT format="png">
    <NAME>Dashboard</NAME>
     <PATH>Dashboard.png</PATH>
     <WEB_PATH>Dashboard.png</WEB_PATH>
    </REPORT>
   </REPORTS>
   ```

1. [!DNL report.cfg]に、pngの出力形式を含めて保存します。 今後は、png形式のレポートを生成する必要があります。

**4.0にアップグ [!DNL Report Server] レードするには**

1. Data Workbenchコンピューター上で、Report Serverのアップグレードファイルを、Data Workbenchがインストールされているディレクトリ内の[!DNL Temp\Software]フォルダーにコピーします。
1. Data Workbenchを起動し、[!DNL Configuration]プロファイルを読み込みます。
1. **[!UICONTROL Configure Connection to Servers]**&#x200B;サムネールをクリックします。
1. [!DNL Servers Manager]で、Data Workbenchサーバーのアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。

1. Softwareフォルダで、 [!DNL Report Server]フォルダを開きます。
1. [!DNL ReportServer.exe]の&#x200B;**[!UICONTROL Temp]**&#x200B;チェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]**>*&#x200B;を選択します。

## レポートサーバー{#section-96eb3281c45a45c0a7065deaa6845c25}のアンインストール

**アンインストールするには[!DNL Report Server]**

1. [!DNL Report Windows]サービスの登録を解除します。

   1. コマンドプロンプトを開き、Data Workbenchサーバーをインストールしたフォルダー内のbinサブディレクトリに移動します(InsightServer64.exe)。 例：[!DNL D:\Adobe\Report\bin]
   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。[!DNL visualreport /unregserver]

1. Report Serverのインストールディレクトリを削除します。
