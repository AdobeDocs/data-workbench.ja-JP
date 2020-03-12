---
description: Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、ここに記載されている手順に従います。
solution: Analytics
title: Data Workbench 5.5 から 6.1 へのアップグレード
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Data Workbench 5.5 から 6.1 へのアップグレード{#data-workbench-to-upgrade}

Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。

**手順 1**：[サーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**手順 2**：[レポートサーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**手順 3**：[クライアントのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>サーバ、レポートサーバ、クライアントの各コンポーネントは、64ビットWindowsオペレーティングシステムで実行するようにアップグレードされます。

## サーバーのアップグレード {#section-08bd6fe3da8740fcb19688e8cac6f223}

Follow these steps to update the **[!UICONTROL Server v6.1]** components:

1. Using the **[!UICONTROL Software and Docs]** profile, open the **[!UICONTROL Start Here]** workspace and download all needed server packages to a local folder.

   * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip folders and extract all files.

      The **[!UICONTROL Server]** package includes **[!UICONTROL Lookup]** and **[!UICONTROL Profile]** folders with the **[!UICONTROL Base]** and **[!UICONTROL Transform]** lookup files to add and replace to update the server.

   * Download new **[!UICONTROL Profiles]** folders.
   * Download updated **[!UICONTROL Lookup]** folders.
   * \パッケージをダ **[!UICONTROL Report Server]** ウンロ **[!UICONTROL v6.1]** ードします。
   * Download additional **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**, and **[!UICONTROL Dashboard]** files as needed for your system.

1. Stop the **[!UICONTROL Adobe Insight Server]** service.

   ![](assets/install_server_download1.png)

1. From the downloaded **[!UICONTROL Server]** package:

   1. Replace the [!DNL Server\Bin] folder to update the [!DNL InsightServer64.exe] and supporting files.

   1. Replace the [!DNL Server\Profiles] folder. ファイルはすべて上書きして構いません。
   1. Update the [!DNL Server\Lookups] folder. 既にフォルダー内にあるカスタムファイルに、新しくダウンロードしたファイルを追加する必要があります。
   1. Replace the [!DNL Server\Software] folder to update [!DNL Insight.exe] and [!DNL ReportServer.exe]

   1. Update the [!DNL Server\Scripts] folder to update [!DNL TnTSend.exe].

1. を使用する場 **[!UICONTROL DeviceAtlas]**&#x200B;合は、フォルダー内のバ [ンドルを更新する](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html) 必要があり [!DNL Server\Lookups] ます。
1. ベクターが更新されて各プロファイルのアイテム数が反映されるように [!DNL Directories] ファイルの [!DNL Profile.cfg] を設定します。

   For example, to enable the **[!UICONTROL Predictive Analytics]** profile you will need to update this setting.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. 予測分析機能をアップグレードするために、[!DNL PAServer.cfg] ファイルを設定し、保存します。

   予測分析ジョブをサーバーに送信する場合は、[!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] ファイルを設定して、サーバー側のクラスタリング送信を管理する必要があります。

   サイトの実装に基づいて [!DNL PAServer.cfg] を設定して保存できるように、カスタムプロファイルは予測分析設定プロファイルから設定を継承する必要があります。

1. Define the **[!UICONTROL Log Source ID]**.

   は、一 **[!UICONTROL Recording of Rows per Log Source]** 意の名前を **[!UICONTROL v6.04]** 付けてカスタムプロファイルのフ [!DNL Log Processing.cfg] ァイルに追加し、定義しました **[!UICONTROL Log Source ID]**。

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   ログソース ID が定義されていない場合は、次のエラーが表示されます。

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. [!DNL EventMessages.dll] が更新されているので、クラスター全体で **[!UICONTROL Adobe Insight Server]** の登録を解除してから、登録し直す必要があります。

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. Start the **[!UICONTROL Adobe Insight Server]** service across the cluster.

これで、サーバーのインストールは完了です。

## レポートサーバーのアップグレード {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>にアップグレードする前 **[!UICONTROL Report Server v6.1]**&#x200B;に、にアップグレードする必要がありま **[!UICONTROL Server v6.1]**&#x200B;す。

1. プロファイル **[!UICONTROL Software and Docs]** を使用して、パッケ **[!UICONTROL v6.1]** ージからロー **[!UICONTROL Report Server]** カルフォルダーにダウンロードします。
1. ダウンロードしたパッケージから **[!UICONTROL Report Server 6.1]** をコピーし、プロファイルパッケージを置き換えます。

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the [!DNL install] folder is a backup file used for localization, and must be present in the [!DNL install] directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.

1. （オプション）全角文字をサポートするようにレポートサーバーの設定ファイルを変更します。

   Data Workbenchは現在、英語(-en-us)と中国語(-zh-cn)をサポートしています。 半角文字と全角文字をサポートするフォントを設定する必要があります。

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   リストしたフォントが Windows オペレーティングシステムにインストールされている必要もあります。

1. 設定 [!DNL Report Server v6.1].

   1. Stop the **[!UICONTROL Adobe Insight Report Server]** service.
   1. 「管理者」としてコマンドプロンプトを起動します。
   1. Report Server の [!DNL install] フォルダーに移動します。
   1. 次のコマンドを使用して、Report Server サービスを削除します。

      ```
      ReportServer.exe /unregserver
      ```

1. 言語設定に応じてサービスを開始します。

   ```
   ReportServer.exe -RegServer -Locale -en-us (English) 
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. Report Serverが正しい設定で実行されていることを確認するには、を開い **[!UICONTROL Windows Service Manager]** て右クリックしま **[!UICONTROL Adobe Insight Report Server - Properties]**&#x200B;す。 実行可能ファイルのパスに、更新されたコマンドライン設定が表示されます。

これで、レポートサーバーのインストールは完了です。

## クライアントのアップグレード {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>Before upgrading to **[!UICONTROL Client v6.1]**, the administrator must first upgrade to **[!UICONTROL Server v6.1.]**

1. [!DNL Insight.exe] を起動しますが、どのプロファイルにも接続しないでください。
1. ソフトウェアが自動的に更新されないように [!DNL Insight.cfg] ファイルを編集します。

   ```
   Update Software = bool: false
   ```

1. プロファイル( **[!UICONTROL Software and Docs]** softdocs)に接続します。
1. ダウンロード [!DNL Software\Insight Client\v6.10].
1. （オプション）全角文字をサポートするように [!DNL insight.cfg] を変更します。

   Data Workbench では、現在、英語と簡体字中国語の両方をサポートしています。これら両方の言語をサポートするフォントを選択します。

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. クライアントを終了します。
1. ダウンロードした **v6.1** クライアントパッケージ内のファイルを [!DNL Install] フォルダーにコピーします。

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the install folder is a backup file used for localization, and must be present in the install directory. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.
   >
   >例えば、簡体字中国語で起動するには、コマンドライン設定で渡すショートカットを作成します。
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >英語（デフォルト）で起動する場合は、コマンドラインの変更は必要ありません。

1. [!DNL Insight.exe]（英語の場合）または他の言語用に作成したショートカットを起動します。
1. プロファイルに接続し、クライアントがサーバーと同期できるようにします。
1. （オプション）IME を使用するには、[!DNL Insight.cfg] ファイルに次の変更を行います。

   ```
   Localized IME = bool: true
   ```

   Input Method Editor（IME）を使用すると、国際文字を入力できます。

1. （オプション）ソフトウェアが自動的に更新されるように [!DNL Insight.cfg] ファイルを編集します。

   ```
   Update Software = bool: true
   ```

   IME の実装手順を参照してください。
1. Restart again after the profile synchronization to employ the most recent [!DNL .zbin] file.

これで、クライアントのインストールは完了です。
