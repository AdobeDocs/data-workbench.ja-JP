---
description: Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。
solution: Analytics
title: Report Serverのアップグレードとアンインストール
topic: Data workbench
uuid: 42f0d190-1a88-424d-be4b-90338144d287
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Report Serverのアップグレードとアンインストール{#upgrading-and-uninstalling-report-server}

Report Serverソフトウェアのアップグレードとアンインストールに関する情報です。

* [レポートのアップグレード](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [レポートのアンインストール](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## Report Serverのアップグレード {#section-95fea4bddad74616a8aea450dcdb2282}

5.4にアップグレードする [!DNL Report Server] 場合は、手順に従ってソフトウェアをアップグレードで [!DNL Report Server] きます。 3.6以前を使用して [!DNL Report Server] いる場合は、アドビにお問い合わせください。

5.4をアップグレ [!DNL Report Server] ードするには、Data Workbenchを使用して、接続先のData Workbenchサーバーにアップグレードファイルをコピー [!DNL Report Server] します。 その後、サーバーインスタンスが [!DNL Report] そのサーバーに接続し、プロファイルを読み込むと、サーバーインスタンスが自動的にアップグレードされます。

>[!NOTE]
>
>アップグレード [!DNL Report Server]する前に、Data Workbenchサーバーソフトウェアと、Data Workbenchサーバーで実行されているプロファイルが正しくアップグレードされていることを確認してください。 詳しくは、Adobe Consulting Services にお問い合わせください。

次の手順を実行するには、まずのアップグレードファイルを取得する必要がありま [!DNL Report Server]す。

**5.4以降のバージ[!DNL Report Server]ョンにアップグレードするには**

1. このディレクトリ内のすべてのファイルのバックアップを作成し、 [!DNL E:\Portal] このディレクトリ内のすべてのファイルとフォルダを削除します。
1. Copy the contents of the new build into [!DNL E:\Portal].
1. 前のセ [!DNL global.asa]クショ [!DNL email.asp]ンの手順 [!DNL TopNavigation.xml] に従って、、およびを変更します。

1. バックアップから [!DNL users.mdb] をコピーします。

   >[!NOTE]
   >
   >以前に.png出力のレポートを生成していない場合は、個々のレポートフォルダーに移動し、pngのレポート形式を含めるよ [!DNL reports.xml] うにを変更する必要があります。 そうしないと、500エラーが発生する場合があります。 元の画像は [!DNL reports.xml] 次のようになります。

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

1. にpngの出 [!DNL report.cfg]力形式を含めて保存します。 今後は、PNG形式でレポートを生成する必要があります。

**4.0にアップグレ[!DNL Report Server]ードするには**

1. Data Workbenchコンピューターで、Data Workbenchがインストールされているディレクトリ内のフ [!DNL Temp\Software] ォルダーにReport Serverのアップグレードファイルをコピーします。
1. data workbenchを起動し、プロファイルを読み込 [!DNL Configuration] みます。
1. サムネールをクリ **[!UICONTROL Configure Connection to Servers]** ックします。
1. で、Data Workbench [!DNL Servers Manager]サーバーのアイコンを右クリックし、をクリックしま **[!UICONTROL Server Files]**&#x200B;す。

1. Softwareフォルダで、フォルダを開き [!DNL Report Server] ます。
1. のチェックマークを **[!UICONTROL Temp]** 右クリックし、 [!DNL ReportServer.exe] / **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

## Report Serverのアンインストール {#section-96eb3281c45a45c0a7065deaa6845c25}

**アンインストールするには[!DNL Report Server]**

1. サービスの登録を [!DNL Report Windows] 解除します。

   1. コマンドプロンプトを開き、Data Workbenchサーバー(InsightServer64.exe)をインストールしたフォルダー内のbinサブディレクトリに移動します。例：[!DNL D:\Adobe\Report\bin]
   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windowsのサービスを停止し、登録解除します。 [!DNL visualreport /unregserver]

1. Report Serverのインストールディレクトリを削除します。

