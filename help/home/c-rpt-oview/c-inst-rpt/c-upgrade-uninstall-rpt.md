---
description: Report Server ソフトウェアのアップグレードとアンインストールに関する情報です。
title: レポートサーバーのアップグレードとアンインストール
uuid: 42f0d190-1a88-424d-be4b-90338144d287
exl-id: 86d0d848-4e2a-45cb-a1b3-b8a856332d33
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 4%

---

# レポートサーバーのアップグレードとアンインストール{#upgrading-and-uninstalling-report-server}

{{eol}}

Report Server ソフトウェアのアップグレードとアンインストールに関する情報です。

* [レポートのアップグレード](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-95fea4bddad74616a8aea450dcdb2282)
* [レポートのアンインストール](../../../home/c-rpt-oview/c-inst-rpt/c-upgrade-uninstall-rpt.md#section-96eb3281c45a45c0a7065deaa6845c25)

## レポートサーバーのアップグレード {#section-95fea4bddad74616a8aea450dcdb2282}

にアップグレードする場合は、 [!DNL Report Server] 5.4、手順に従って [!DNL Report Server] ソフトウェア 次を使用する場合： [!DNL Report Server] 3.6 以前の場合は、Adobeにアップグレードのサポートを依頼してください。

アップグレードするには [!DNL Report Server] 5.4。data workbench を使用して、アップグレードファイルをコピー先の data workbench サーバーにコピーする [!DNL Report Server] 接続します。 そうした後 [!DNL Report] サーバーインスタンスは、そのサーバーに接続してプロファイルを読み込むと、自動的にアップグレードされます。

>[!NOTE]
>
>アップグレードする前に [!DNL Report Server]を使用する場合は、data workbench サーバーソフトウェアと、data workbench サーバー上で実行されているプロファイルが正しくアップグレードされていることを確認してください。 詳しくは、Adobe Consulting Services にお問い合わせください。

以下の手順を実行するには、まずのアップグレードファイルを入手する必要があります。 [!DNL Report Server].

**にアップグレードするには [!DNL Report Server] 5.4 以降のバージョン**

1. の下にあるすべてのファイルのバックアップを作成します [!DNL E:\Portal] このディレクトリ内のすべてのファイルとフォルダを削除します。
1. 新しいビルドの内容を次にコピーします。 [!DNL E:\Portal].
1. 変更 [!DNL global.asa], [!DNL email.asp]、および [!DNL TopNavigation.xml] 前の節の説明に従って。

1. を [!DNL users.mdb] バックアップから

   >[!NOTE]
   >
   >.png 出力を含むレポートを生成したことがない場合は、個々のレポートフォルダーに移動し、 [!DNL reports.xml] :png のレポート形式を含めます。 そうしないと、500 エラーが発生する場合があります。 オリジナル [!DNL reports.xml] 次のようになります。

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

1. 内 [!DNL report.cfg]には、png の出力形式を含めて保存します。 今後は、png 形式のレポートを生成する必要があります。

**にアップグレードするには [!DNL Report Server] 4.0**

1. Data Workbench コンピューター上で、Report Server のアップグレードファイルを [!DNL Temp\Software] data workbench がインストールされているディレクトリ内のフォルダー。
1. Data Workbench を起動し、 [!DNL Configuration] プロファイル。
1. 次をクリック： **[!UICONTROL Configure Connection to Servers]** サムネール。
1. 内 [!DNL Servers Manager]をクリックし、 data workbench サーバーのアイコンを右クリックして、 **[!UICONTROL Server Files]**.

1. Software フォルダで、 [!DNL Report Server] フォルダー。
1. を右クリックします。 **[!UICONTROL Temp]** チェックマーク [!DNL ReportServer.exe] を選択し、 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## レポートサーバーのアンインストール {#section-96eb3281c45a45c0a7065deaa6845c25}

**アンインストールするには[!DNL Report Server]**

1. 登録解除 [!DNL Report Windows] サービス。

   1. コマンドプロンプトを開き、Data Workbench サーバー (InsightServer64.exe) をインストールしたフォルダー内の bin サブディレクトリに移動します。 例：[!DNL D:\Adobe\Report\bin]
   1. コマンドプロンプトで、次のコマンドを実行して、Microsoft Windows でサービスとして停止および登録解除します。 [!DNL visualreport /unregserver]

1. Report Server のインストールディレクトリを削除します。
