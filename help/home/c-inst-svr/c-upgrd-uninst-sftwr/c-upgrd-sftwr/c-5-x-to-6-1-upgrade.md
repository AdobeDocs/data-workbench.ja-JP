---
description: Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、ここに記載されている手順に従います。
title: Data Workbench 5.5 から 6.1 へのアップグレード
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 58%

---

# Data Workbench 5.5 から 6.1 へのアップグレード{#data-workbench-to-upgrade}

{{eol}}

Insight v5.5x インストールから Data Workbench v6.1 にアップデートするには、次の手順に従います。

**手順 1**：[サーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**手順 2**：[レポートサーバーのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**手順 3**：[クライアントのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>サーバー、レポートサーバー、およびクライアントコンポーネントは、64 ビット Windows オペレーティングシステムで実行するようにアップグレードされます。

## サーバーのアップグレード {#section-08bd6fe3da8740fcb19688e8cac6f223}

以下の手順に従って、 **[!UICONTROL Server v6.1]** コンポーネント：

1. の使用 **[!UICONTROL Software and Docs]** プロファイルを開くには、 **[!UICONTROL Start Here]** ワークスペースを開き、必要なすべてのサーバーパッケージをローカルフォルダーにダウンロードします。

   * ダウンロード **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip フォルダーを展開し、すべてのファイルを抽出します。

      この **[!UICONTROL Server]** パッケージに含まれる **[!UICONTROL Lookup]** および **[!UICONTROL Profile]** フォルダーと **[!UICONTROL Base]** および **[!UICONTROL Transform]** 追加および置換する参照ファイルで、サーバーを更新します。

   * 新規をダウンロード **[!UICONTROL Profiles]** フォルダー。
   * 更新されたダウンロード **[!UICONTROL Lookup]** フォルダー。
   * をダウンロードします。 **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** パッケージ。
   * 追加の **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**、および **[!UICONTROL Dashboard]** 必要に応じて、システムに必要なファイルを保存します。

1. を停止します。 **[!UICONTROL Adobe Insight Server]** サービス。

   ![](assets/install_server_download1.png)

1. ダウンロードした **[!UICONTROL Server]** パッケージ：

   1. を [!DNL Server\Bin] 更新するフォルダー [!DNL InsightServer64.exe] およびサポートファイル。

   1. を [!DNL Server\Profiles] フォルダー。 ファイルはすべて上書きして構いません。
   1. を更新します。 [!DNL Server\Lookups] フォルダー。 既にフォルダー内にあるカスタムファイルに、新しくダウンロードしたファイルを追加する必要があります。
   1. を [!DNL Server\Software] 更新するフォルダー [!DNL Insight.exe] および [!DNL ReportServer.exe]

   1. を更新します。 [!DNL Server\Scripts] 更新するフォルダー [!DNL TnTSend.exe].

1. 次を使用する場合： **[!UICONTROL DeviceAtlas]**&#x200B;を選択した場合、 [バンドルを更新](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) ～に位置する [!DNL Server\Lookups] フォルダー。
1. ベクターが更新されて各プロファイルのアイテム数が反映されるように [!DNL Directories] ファイルの [!DNL Profile.cfg] を設定します。

   例えば、 **[!UICONTROL Predictive Analytics]** プロファイルを更新する必要があります。

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

1. 次を定義： **[!UICONTROL Log Source ID]**.

   この **[!UICONTROL Recording of Rows per Log Source]** が **[!UICONTROL v6.04]** カスタムプロファイルの [!DNL Log Processing.cfg] 一意の名前を付けた **[!UICONTROL Log Source ID]**.

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

1. を開始します。 **[!UICONTROL Adobe Insight Server]** クラスター全体のサービス。

これで、サーバーのインストールは完了です。

## レポートサーバーのアップグレード {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>にアップグレードする前に **[!UICONTROL Report Server v6.1]**&#x200B;を使用する場合は、最初に **[!UICONTROL Server v6.1]**.

1. の使用 **[!UICONTROL Software and Docs]** プロファイル、ダウンロード **[!UICONTROL v6.1]** から **[!UICONTROL Report Server]** ローカルフォルダーにパッケージ化します。
1. ダウンロードしたパッケージから **[!UICONTROL Report Server 6.1]** をコピーし、プロファイルパッケージを置き換えます。

   >[!NOTE]
   >
   >この [!DNL Insight.zbin] ファイルを [!DNL install] フォルダーは、ローカライゼーションに使用されるバックアップファイルで、 [!DNL install] ディレクトリ。 このファイルまたはその他 [!DNL .zbin] ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。

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

   1. を停止します。 **[!UICONTROL Adobe Insight Report Server]** サービス。
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

1. Report Server が正しい設定で実行されていることを確認するには、を開きます。 **[!UICONTROL Windows Service Manager]** 右クリック **[!UICONTROL Adobe Insight Report Server - Properties]**. 実行可能ファイルのパスに、更新されたコマンドライン設定が表示されます。

これで、レポートサーバーのインストールは完了です。

## クライアントのアップグレード {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>にアップグレードする前に **[!UICONTROL Client v6.1]**&#x200B;の場合、管理者はまず **[!UICONTROL Server v6.1.]**

1. [!DNL Insight.exe] を起動しますが、どのプロファイルにも接続しないでください。
1. ソフトウェアが自動的に更新されないように [!DNL Insight.cfg] ファイルを編集します。

   ```
   Update Software = bool: false
   ```

1. 接続先 **[!UICONTROL Software and Docs]** プロファイル (softdocs)。
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
   >この [!DNL Insight.zbin] install フォルダー内のファイルは、ローカリゼーションに使用されるバックアップファイルで、 install ディレクトリに存在する必要があります。 このファイルまたはその他 [!DNL .zbin] ファイルは、起動時に渡されるコマンドライン設定に応じて使用されます。
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
1. 最新の [!DNL .zbin] ファイル。

これで、クライアントのインストールは完了です。
