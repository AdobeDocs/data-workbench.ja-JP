---
description: Data Workbench v6.0x インストールから Data Workbench v6.1 にアップデートするには、ここに記載されている手順に従います。
solution: Analytics
title: Data Workbench 6.0 から 6.1 へのアップグレード
topic: Data workbench
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Data Workbench 6.0 から 6.1 へのアップグレード{#data-workbench-to-upgrade}

Data Workbench v6.0x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。

**手順 1**：[サーバーのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**手順 2**：[レポートサーバーのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**手順 3**：[クライアントのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>サーバ、レポートサーバ、クライアントの各コンポーネントは、64ビットWindowsオペレーティングシステムで実行するようにアップグレードされます。

## サーバーのアップグレード {#section-7845393f76214aa7ad53ac4b2cca9e5b}

Follow these steps to update the **[!UICONTROL Server v6.1]** components:

1. Using the **[!UICONTROL Software and Docs]** profile, open the **[!UICONTROL Start Here]** workspace and download all needed server packages to a local folder.

   * Download **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip folders and extract all files.

      The Server package includes **[!UICONTROL Lookup]** and **[!UICONTROL Profile]** folders with **[!UICONTROL Base]** and **[!UICONTROL Transform]** profiles to update the server.

      * Download the **[!UICONTROL Profiles]** folders.
      * Download the **[!UICONTROL Lookup]** folders.
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

1. ベクターが更新されて各プロファイルのアイテム数が反映されるように [!DNL Profile.cfg] ファイルを設定します。

   For example, to enable the **[!UICONTROL Predictive Analytics]** profile you will need to update this setting.

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. 予測分析機能用に PAServer.cfg ファイルを設定し、保存します。

   予測分析ジョブをサーバーに送信する場合は、[!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] ファイルを設定して、サーバー側のクラスタリング送信を管理する必要があります。

   サイトの実装に基づいて [!DNL PAServer.cfg] ファイルを設定して保存できるように、カスタムプロファイルは予測分析設定プロファイルから設定を継承する必要があります。

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

1. （オプション）Data Workbenchは現在、英語(-en-us)と中国語(-zh-cn)をサポートしています。 半角文字と全角文字をサポートするフォントを設定する必要があります。

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   リストしたフォントが Windows オペレーティングシステムにインストールされている必要もあります。

1. ローカリゼー [!DNL Report Server v6.1] ションを設定します。

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
>Before upgrading to **[!UICONTROL Client v6.1]**, the administrator must first upgrade to **[!UICONTROL Insight Server v6.1.]**

1. [!DNL Insight.exe] を起動しますが、どのプロファイルにも接続しないでください。
1. Edit the [!DNL Insight.cfg] file.

   ```
   Update Software = bool: true
   ```

1. プロファイルに接続します。

   クライアントがサーバーと同期できるようにします。最新の v6.1 クライアントプロファイル、実行可能ファイルおよび設定ファイルを使用してクライアントがアップグレードされます。

   >[!NOTE]
   >
   >The [!DNL Insight.zbin] file in the [!DNL install] folder is a backup file used for localization and must be present. This file or other [!DNL .zbin] files will be used depending on the command-line settings passed when starting up.

   See [setting up localized languages](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) to add an [!DNL insight.zbin] file required for localized settings.

**追加のクライアント設定**

[!DNL Insight.exe] およびサポートファイルを設定する前に、クライアントアプリケーションを終了する必要があります。

簡体字中国語をインストールするには：

1. コマンドライン設定で [!DNL Insight.exe] ファイルに渡すショートカットを作成します。

   ```
   Insight.exe -zh-cn
   ```

1. 半角および全角フォント文字をサポートするように [!DNL Insight.cfg] を設定します。

   Data Workbench では、現在、英語と簡体字中国語の両方をサポートしています。これら両方の言語をサポートするフォントを選択できます。

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

   要求したフォントを Windows オペレーティングシステムにインストールする必要もあります。

1. 作成したショートカットを起動して、プロファイルと更新された . [!DNL zbin] file.

Input Method Editor（IME）を使用するには：

IME を使用すると、国際文字を入力できます。

1. 次の設定で [!DNL Insight.cfg] ファイルを更新します。

   ```
   Localized IME = bool: true
   ```

1. Launch the shortcut that you created to synchronize profiles and the updated [!DNL .zbin] file.

これで、クライアントのインストールは完了です。
