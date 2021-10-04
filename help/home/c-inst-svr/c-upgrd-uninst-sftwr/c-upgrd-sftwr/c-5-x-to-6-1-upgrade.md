---
description: Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。
title: Data Workbench 5.5 から 6.1 へのアップグレード
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 58%

---

# Data Workbench 5.5 から 6.1 へのアップグレード{#data-workbench-to-upgrade}

Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。

**手順 1**：[サーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**手順 2**：[レポートサーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**手順 3**：[クライアントのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>サーバー、レポートサーバー、およびクライアントコンポーネントは、64 ビット Windows オペレーティングシステムで実行するようにアップグレードされます。

## サーバーのアップグレード {#section-08bd6fe3da8740fcb19688e8cac6f223}

次の手順に従って、**[!UICONTROL Server v6.1]** コンポーネントを更新します。

1. **[!UICONTROL Software and Docs]** プロファイルを使用して、**[!UICONTROL Start Here]** ワークスペースを開き、必要なすべてのサーバーパッケージをローカルフォルダーにダウンロードします。

   * **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip フォルダーをダウンロードし、すべてのファイルを展開します。

      **[!UICONTROL Server]** パッケージには、**[!UICONTROL Lookup]** と **[!UICONTROL Profile]** フォルダーが含まれ、**[!UICONTROL Base]** と **[!UICONTROL Transform]** 参照ファイルが追加されて、サーバーを更新するために置き換えられます。

   * 新しい **[!UICONTROL Profiles]** フォルダーをダウンロードします。
   * 更新された **[!UICONTROL Lookup]** フォルダーをダウンロードします。
   * **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** パッケージをダウンロードします。
   * 必要に応じて、追加の **[!UICONTROL Sensor]**、**[!UICONTROL Documentation]**、**[!UICONTROL Dashboard]** ファイルをダウンロードします。

1. **[!UICONTROL Adobe Insight Server]** サービスを停止します。

   ![](assets/install_server_download1.png)

1. ダウンロードした **[!UICONTROL Server]** パッケージから、次の手順を実行します。

   1. [!DNL Server\Bin] フォルダーを置き換えて、[!DNL InsightServer64.exe] とサポートファイルを更新します。

   1. [!DNL Server\Profiles] フォルダーを置き換えます。 ファイルはすべて上書きして構いません。
   1. [!DNL Server\Lookups] フォルダーを更新します。 既にフォルダー内にあるカスタムファイルに、新しくダウンロードしたファイルを追加する必要があります。
   1. [!DNL Server\Software] フォルダーを置き換えて [!DNL Insight.exe] と [!DNL ReportServer.exe] を更新します。

   1. [!DNL Server\Scripts] フォルダーを更新して [!DNL TnTSend.exe] を更新します。

1. **[!UICONTROL DeviceAtlas]** を採用する場合は、[!DNL Server\Lookups] フォルダーにある [bundle](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) を更新する必要があります。
1. ベクターが更新されて各プロファイルのアイテム数が反映されるように [!DNL Directories] ファイルの [!DNL Profile.cfg] を設定します。

   例えば、**[!UICONTROL Predictive Analytics]** プロファイルを有効にするには、この設定を更新する必要があります。

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

1. **[!UICONTROL Log Source ID]** を定義します。

   **[!UICONTROL Recording of Rows per Log Source]** が **[!UICONTROL v6.04]** に追加され、一意の名前 **[!UICONTROL Log Source ID]** を追加することで、カスタムプロファイルの [!DNL Log Processing.cfg] ファイルに定義されます。

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

1. クラスター全体で **[!UICONTROL Adobe Insight Server]** サービスを開始します。

これで、サーバーのインストールは完了です。

## レポートサーバーのアップグレード {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>**[!UICONTROL Report Server v6.1]** にアップグレードする前に、まず **[!UICONTROL Server v6.1]** にアップグレードする必要があります。

1. **[!UICONTROL Software and Docs]** プロファイルを使用して、**[!UICONTROL Report Server]** パッケージから **[!UICONTROL v6.1]** をローカルフォルダーにダウンロードします。
1. ダウンロードしたパッケージから **[!UICONTROL Report Server 6.1]** をコピーし、プロファイルパッケージを置き換えます。

   >[!NOTE]
   >
   >[!DNL install] フォルダーの [!DNL Insight.zbin] ファイルは、ローカライゼーションに使用されるバックアップファイルで、 [!DNL install] ディレクトリに存在する必要があります。 このファイルや他の [!DNL .zbin] ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。

1. （オプション）全角文字をサポートするようにレポートサーバーの設定ファイルを変更します。

   Data Workbench は、現在、英語 (-en-us) と中国語 (-zh-cn) をサポートしています。 半角文字と全角文字をサポートするフォントを設定する必要があります。

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   リストしたフォントが Windows オペレーティングシステムにインストールされている必要もあります。

1. 設定 [!DNL Report Server v6.1].

   1. **[!UICONTROL Adobe Insight Report Server]** サービスを停止します。
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

1. Report Server が正しい設定で実行されていることを確認するには、**[!UICONTROL Windows Service Manager]** を開き、**[!UICONTROL Adobe Insight Report Server - Properties]** を右クリックします。 実行可能ファイルのパスに、更新されたコマンドライン設定が表示されます。

これで、レポートサーバーのインストールは完了です。

## クライアントのアップグレード {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>**[!UICONTROL Client v6.1]** にアップグレードする前に、管理者はまず **[!UICONTROL Server v6.1.]** にアップグレードする必要があります

1. [!DNL Insight.exe] を起動しますが、どのプロファイルにも接続しないでください。
1. ソフトウェアが自動的に更新されないように [!DNL Insight.cfg] ファイルを編集します。

   ```
   Update Software = bool: false
   ```

1. **[!UICONTROL Software and Docs]** プロファイル (softdocs) に接続します。
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
   >install フォルダー内の [!DNL Insight.zbin] ファイルは、ローカライゼーションに使用されるバックアップファイルで、install ディレクトリに存在する必要があります。 このファイルや他の [!DNL .zbin] ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。
   >
   >例えば、簡体字中国語で起動するには、コマンドライン設定で渡すショートカットを作成します。
   >
   >
   ```
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
1. 最新の [!DNL .zbin] ファイルを使用するために、プロファイルの同期後に再起動します。

これで、クライアントのインストールは完了です。
