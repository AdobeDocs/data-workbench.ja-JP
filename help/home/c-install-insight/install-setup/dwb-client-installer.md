---
description: Data Workbench には、ワークステーション（クライアント）アプリケーションをインストールするためのセットアップウィザードがあります。
title: ワークステーションセットアップウィザード
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークステーションセットアップウィザード{#workstation-setup-wizard}

Data Workbench には、ワークステーション（クライアント）アプリケーションをインストールするためのセットアップウィザードがあります。

## セットアップウィザードを使用したワークステーションのインストール {#section-58da9bb6196c46eab3b54146913fdcb8}

インストールウィザードの実行可能ファイルを起動して、各ステップを順に実行し、ワークステーションクライアントプログラムをインストールします。ワークステーションをインストールしたら、サーバーとプロファイルに接続できます。

1. ワークステーションインストーラーの実行可能ファイルをダブルクリックします。
1. 「**はい**」をクリックして、Windows へのプログラムのインストールを許可します。
1. セットアップウィザードの&#x200B;**言語**&#x200B;を選択します。

   ウィザードが開きます。

   ![](assets/6_4_workstation_wizard.png)

1. **Data Workbench セットアップウィザードの開始** ダイアログで「**次へ**」をクリックします。

1. **新規インストール**&#x200B;するか、既存インストールを&#x200B;**アップグレードまたは修復**&#x200B;するかを選択します。

   **新規インストール**&#x200B;は、以前インストールされたファイルをすべて上書きします。

   **アップグレード**&#x200B;は、ワークステーションを最新バージョンに更新するか、既存インストールを修復できるようにします。Data Workbench は、インストールされている **Insight.exe** ファイルを比較して、新しいバージョンのクライアントがある場合はワークステーションセットアップウィザードを実行します。

1. インストール場所を選択します。

   「**標準**」を選択すると、デフォルトのフォルダーおよび場所にインストールされます。

   * プログラムファイルはデフォルトで次の場所に保存されます。

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * データファイル（プロファイル、証明書、トレースログ、ユーザーファイル）はデフォルトで次の場所に保存されます。

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >A generic ***Insight.cfg*** file without server details will be installed initially. 以前のインストールからファイルを移動するのではなく、新たにインストールされた ***Insight.cfg*** ファイルを使用してカスタマイズすることをお勧めします。Because the path for installing the workstation has changed, the addition of fonts, removal of the *User Folder*, and the removal of the *TraceFileComponent * is recommended.

1. （オプション）「** Custom**」を選択して、言語パッケージと、プログラムおよびデータファイルの場所を選択します。
1. **スタートメニューのショートカット**&#x200B;の場所を選択します。

   ![](assets/6_4_workstation_wizard_folder.png)

   Windows のスタートメニューにショートカットをインストールしないようにするには、「**スタートメニューに追加しない**」をクリックします。

1. 「**次へ」をクリックします。**」をクリックします。選択したファイル位置のパスと言語に関する要約が表示されます。「**インストール**」をクリックします。

1. **Data Workbench 証明書**&#x200B;を探します。

   インストール中に Data Workbench 証明書が見つからなかった場合は、証明書（デフォルトではクライアントの **Certificates** フォルダーにある **.pem** ファイル）の場所を参照するためのダイアログが開きます。または、「**スキップp**」をクリックして、インストール後に証明書を探します。

   証明書が見つかったら、「**インストール**」をクリックします。

1. セットアップウィザードが完了し、Data Workbench がインストールされたら、「**完了**」をクリックしてセットアップを完了します。

   >[!NOTE]
   >
   >The default log location for the Workstation Set up Wizard at **[!DNL C:\Users\`<userName>&#39;\AppData\Local\Temp ]**

   セットアップ後に Data Workbench を開くには、「**アプリケーションを起動**」チェックボックスをオンにします。

1. **ファイル内のサーバ** ーへの接続を設定 **[!DNL Insight.cfg]** します。

   ワークステーションをインストールすると、ワークステーション設定エクスペリエンスの強化ワークスペースが開き、*Insight.cfg* ファイル内の[サーバー接続情報の入力](/help/home/c-get-started/c-insght-config-param.md)に関する追加情報と、ドロップダウンからプロファイルを選択するためのオプションが表示されます。サーバーへの接続状況も表示されます。

   ![](assets/6_4_workstation_install_conf_conn.png)

## インストールフォルダー {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Data Workbench のフォルダー構造には、2 つのインストール場所があります。

* **プログラムファイル****Insight.exe** ファイルおよびクライアントをサポートするファイル（**Insight.ini**）は、デフォルトで次の場所に配置されるようになりました。

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* **Appdata** フォルダー

   **Insight.cfg**、プロファイル、証明書、トレースログおよびユーザーファイルは、デフォルトで次の場所に配置されるようになりました。

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   **Appdata** フォルダーのパスを `Insight.ini` ファイル内に設定できます。

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## ワークステーションのアンインストール {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench now includes an executable to uninstall the workstation (located by default at **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

ハードドライブから起動して、Data Workbench ワークステーションファイルを削除するためのステップに従います。

>[!NOTE]
>
>You can launch the **unins000.exe** executable from the folder, using the **Uninstall Data Workbench** shortcut from Start Menu, or from **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
