---
description: Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。
title: レポートサーバーのアップグレードとアンインストール
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# レポートサーバーのアップグレードとアンインストール{#upgrading-and-uninstalling-report-server}

Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。

* [レポートのアップグレード](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [レポートのアンインストール](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## レポートサーバーをアップグレード{#section-95fea4bddad74616a8aea450dcdb2282}

[!DNL Report Server] 5.4にアップグレードする場合は、[!DNL Report Server]ソフトウェアのアップグレード手順を使用できます。 [!DNL Report Server] 3.6以前を使用している場合は、Adobeに問い合わせて、アップグレードに関するサポートを依頼してください。

[!DNL Report Server] 5.4をアップグレードするには、data workbenchを使用して、[!DNL Report Server]の接続先のdata workbenchサーバーにアップグレードファイルをコピーします。 その後、[!DNL Report]サーバーインスタンスがそのサーバーに接続してプロファイルを読み込むと、自動的にサーバーインスタンスが自動的にアップグレードされます。

>[!NOTE]
>
>[!DNL Report Server]をアップグレードする前に、data workbenchサーバーソフトウェアと、data workbenchサーバーで実行されているプロファイルが正しくアップグレードされていることを確認してください。 詳しくは、Adobe Consulting Services にお問い合わせください。

次の手順を実行するには、まず[!DNL Report Server]のアップグレードファイルを取得する必要があります。

**5.4以降のバージョ [!DNL Report Server] ンにアップグレードするには**

1. [!DNL E:\Portal]の下にあるすべてのファイルのバックアップを作成し、このディレクトリ内のすべてのファイルとフォルダーを削除します。
1. 新しいビルドの内容を[!DNL E:\Portal]にコピーします。
1. 前の節の説明に従って、[!DNL global.asa]、[!DNL email.asp]、[!DNL TopNavigation.xml]を変更します。

1. バックアップから[!DNL users.mdb]をコピーします。

   >[!NOTE]
   >
   >.png出力を使用したレポートを以前に生成していない場合は、個々のレポートフォルダーに移動し、[!DNL reports.xml]を変更してpngのレポート形式を含める必要があります。 そうしないと、500エラーが発生する場合があります。 元の[!DNL reports.xml]は次のようになります。

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

1. [!DNL report.cfg]にpngの出力形式を含めて保存します。 今後は、png形式のレポートを生成する必要があります。

**4.0にアップグレード [!DNL Report Server] するには**

1. Data Workbenchコンピューター上で、Data Workbenchがインストールされているディレクトリ内の[!DNL Temp\Software]フォルダーにReport Serverアップグレードファイルをコピーします。
1. 開始のdata workbenchを起動し、[!DNL Configuration]プロファイルを読み込みます。
1. **[!UICONTROL Configure Connection to Servers]**&#x200B;サムネールをクリックします。
1. [!DNL Servers Manager]で、data workbenchサーバーのアイコンを右クリックし、**[!UICONTROL Server Files]**&#x200B;をクリックします。

1. Softwareフォルダーで、[!DNL Report Server]フォルダーを開きます。
1. [!DNL ReportServer.exe]の&#x200B;**[!UICONTROL Temp]**&#x200B;チェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]**>*&#x200B;を選択します。

## レポートサーバーのアンインストール{#section-96eb3281c45a45c0a7065deaa6845c25}

**をアンインストールするには[!DNL Report Server]**

1. [!DNL Report Windows]サービスの登録を解除します。

   1. コマンドプロンプトを開き、Data Workbenchサーバー(InsightServer64.exe)をインストールしたフォルダー内のbinサブディレクトリに移動します。 例：[!DNL D:\Adobe\Report\bin]
   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスとして停止および登録解除します。[!DNL visualreport /unregserver]

1. Report Serverのインストールディレクトリを削除します。
