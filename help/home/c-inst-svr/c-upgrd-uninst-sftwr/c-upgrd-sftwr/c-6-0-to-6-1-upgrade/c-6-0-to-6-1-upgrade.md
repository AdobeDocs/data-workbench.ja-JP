---
description: Data Workbench v6.0x インストールから Data Workbench v6.1 にアップデートするには、ここに記載されている手順に従います。
title: Data Workbench 6.0 から 6.1 へのアップグレード
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 56%

---

# Data Workbench 6.0 から 6.1 へのアップグレード{#data-workbench-to-upgrade}

Data Workbench v6.0x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。

**手順 1**：[サーバーのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**手順 2**：[レポートサーバーのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**手順 3**：[クライアントのアップグレード](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>アップグレード後のサーバー、レポートサーバー、クライアントコンポーネントは、64ビットWindowsオペレーティングシステム上で動作します。

## サーバーのアップグレード {#section-7845393f76214aa7ad53ac4b2cca9e5b}

**[!UICONTROL Server v6.1]**&#x200B;コンポーネントを更新するには、次の手順に従います。

1. **[!UICONTROL Software and Docs]**&#x200B;プロファイルーを使用して&#x200B;**[!UICONTROL Start Here]**&#x200B;ワークスペースを開き、必要なすべてのサーバーパッケージをローカルフォルダーにダウンロードします。

   * **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zipフォルダーをダウンロードし、すべてのファイルを展開します。

      Serverパッケージには、**[!UICONTROL Lookup]**&#x200B;フォルダーと&#x200B;**[!UICONTROL Profile]**&#x200B;プロファイルーが含まれ、その中に&#x200B;**[!UICONTROL Base]**&#x200B;フォルダーと&#x200B;**[!UICONTROL Transform]**&#x200B;フォルダーがあり、サーバーを更新します。

      * **[!UICONTROL Profiles]**&#x200B;フォルダーをダウンロードします。
      * **[!UICONTROL Lookup]**&#x200B;フォルダーをダウンロードします。
      * **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**&#x200B;パッケージをダウンロードします。
      * 必要に応じて、追加の&#x200B;**[!UICONTROL Sensor]**、**[!UICONTROL Documentation]**、および&#x200B;**[!UICONTROL Dashboard]**&#x200B;ファイルをダウンロードします。

1. **[!UICONTROL Adobe Insight Server]**&#x200B;サービスを停止します。

   ![](assets/install_server_download1.png)

1. ダウンロードした&#x200B;**[!UICONTROL Server]**&#x200B;パッケージから、次の操作を行います。

   1. [!DNL Server\Bin]フォルダーを置き換えて、[!DNL InsightServer64.exe]とサポートファイルを更新します。

   1. [!DNL Server\Profiles]フォルダーを置き換えます。 ファイルはすべて上書きして構いません。
   1. [!DNL Server\Lookups]フォルダーを更新します。 既にフォルダー内にあるカスタムファイルに、新しくダウンロードしたファイルを追加する必要があります。
   1. [!DNL Server\Software]フォルダーを置き換えて[!DNL Insight.exe]と[!DNL ReportServer.exe]を更新します
   1. [!DNL Server\Scripts]フォルダーを更新して[!DNL TnTSend.exe]を更新します。

1. **[!UICONTROL DeviceAtlas]**&#x200B;を採用する場合は、[!DNL Server\Lookups]フォルダーにあるバンドル](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html)を[更新する必要があります。

1. ベクターが更新されて各プロファイルのアイテム数が反映されるように [!DNL Profile.cfg] ファイルを設定します。

   例えば、**[!UICONTROL Predictive Analytics]**&#x200B;プロファイルを有効にするには、この設定を更新する必要があります。

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

1. **[!UICONTROL Log Source ID]**&#x200B;を定義します。

   **[!UICONTROL Recording of Rows per Log Source]**&#x200B;は&#x200B;**[!UICONTROL v6.04]**&#x200B;に追加され、カスタムプロファイルの[!DNL Log Processing.cfg]ファイルで一意の&#x200B;**[!UICONTROL Log Source ID]**&#x200B;を追加することによって定義されます。

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

1. クラスター全体で&#x200B;**[!UICONTROL Adobe Insight Server]**&#x200B;サービスを開始します。

これで、サーバーのインストールは完了です。

## レポートサーバーのアップグレード  {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>**[!UICONTROL Report Server v6.1]**&#x200B;にアップグレードする前に、まず&#x200B;**[!UICONTROL Server v6.1]**&#x200B;にアップグレードする必要があります。

1. **[!UICONTROL Software and Docs]**&#x200B;プロファイルーを使用して、**[!UICONTROL Report Server]**&#x200B;パッケージから&#x200B;**[!UICONTROL v6.1]**&#x200B;をローカルフォルダーにダウンロードします。

1. ダウンロードしたパッケージから **[!UICONTROL Report Server 6.1]** をコピーし、プロファイルパッケージを置き換えます。

   >[!NOTE]
   >
   >[!DNL install]フォルダー内の[!DNL Insight.zbin]ファイルは、ローカライゼーションに使用するバックアップファイルで、[!DNL install]ディレクトリに存在する必要があります。 このファイルまたは他の[!DNL .zbin]ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。

1. （オプション）Data Workbenchでは、現在、英語(-en-us)と中国語(-zh-cn)をサポートしています。 半角文字と全角文字をサポートするフォントを設定する必要があります。

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   リストしたフォントが Windows オペレーティングシステムにインストールされている必要もあります。

1. ローカライゼーション用に[!DNL Report Server v6.1]を設定します。

   1. **[!UICONTROL Adobe Insight Report Server]**&#x200B;サービスを停止します。
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

1. Report Serverが正しい設定で実行されていることを確認するには、**[!UICONTROL Windows Service Manager]**&#x200B;を開き、**[!UICONTROL Adobe Insight Report Server - Properties]**&#x200B;を右クリックします。 実行可能ファイルのパスに、更新されたコマンドライン設定が表示されます。

これで、レポートサーバーのインストールは完了です。

## クライアントのアップグレード {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>**[!UICONTROL Client v6.1]**&#x200B;にアップグレードする前に、管理者はまず&#x200B;**[!UICONTROL Insight Server v6.1.]**&#x200B;にアップグレードする必要があります

1. [!DNL Insight.exe] を起動しますが、どのプロファイルにも接続しないでください。
1. [!DNL Insight.cfg]ファイルを編集します。

   ```
   Update Software = bool: true
   ```

1. プロファイルに接続します。

   クライアントがサーバーと同期できるようにします。最新の v6.1 クライアントプロファイル、実行可能ファイルおよび設定ファイルを使用してクライアントがアップグレードされます。

   >[!NOTE]
   >
   >[!DNL install]フォルダー内の[!DNL Insight.zbin]ファイルは、ローカライゼーションに使用するバックアップファイルです。このファイルが存在する必要があります。 このファイルまたは他の[!DNL .zbin]ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。

   ローカライズされた設定に必要な[!DNL insight.zbin]ファイルを追加するには、[ローカライズされた言語の設定](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e)を参照してください。

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

1. 作成したショートカットを起動して、プロファイルと更新した[!DNL .zbin]ファイルを同期します。

これで、クライアントのインストールは完了です。
