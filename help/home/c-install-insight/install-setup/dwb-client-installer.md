---
description: Data Workbenchには、ワークステーション（クライアント）アプリケーションをインストールするためのセットアップウィザードが用意されています。
title: ワークステーションセットアップウィザード
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# ワークステーションセットアップウィザード{#workstation-setup-wizard}

Data Workbenchには、ワークステーション（クライアント）アプリケーションをインストールするためのセットアップウィザードが用意されています。

## セットアップウィザードを使用したワークステーションのインストール {#section-58da9bb6196c46eab3b54146913fdcb8}

インストールウィザードの実行ファイルを起動し、各手順を実行して、ワークステーションクライアントプログラムをインストールします。 ワークステーションのインストール後、サーバーとプロファイルに接続

1. 重複 — ワークステーションインストーラの実行可能ファイルをクリックします。
1. 「はい **** 」をクリックして、プログラムのWindowsへのインストールを許可します。
1. セットアップウ **ィザードの** 「言語」を選択します。

   ウィザードが開きます。

   ![](assets/6_4_workstation_wizard.png)

1. Data Workbenchセッ **トアップ** ウィザード **の開始ダイアログで「次へ** 」をクリックします。

1. [新規インストール]をインスト **ールするか** 、既存のイ **ンストールをアップグレード** 、または修復するかを選択します。

   **[新規インストール]を選択すると** 、以前にインストールされたファイルが上書きされます。

   **アップグレード** ：ワークステーションを最新バージョンに更新するか、既存のインストールを修復できます。 Data Workbenchは、インストールされた **Insight.exe** Clientファイルを比較し、新しいバージョンのクライアントが使用可能な場合は、ワークステーションセットアップウィザードを実行します。

1. インストール場所の選択：

   **「標準」は** 、デフォルトのフォルダと場所にインストールされます。

   * プログラムファイルはデフォルトで次の場所に保存されます。

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * データファイル(プロファイル、証明書、トレースログ、ユーザーファイル)は、デフォルトで次の場所に保存されます。

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >サーバーの詳細を含まない汎用 ***的なInsight.cfg*** ファイルが最初にインストールされます。 以前のインストールからファイルを移動するのではなく、新しくインストールした ***Insight.cfgファイルを使用して*** 、カスタマイズすることをお勧めします。 ワークステーションのインストールパスが変更されたので、フォントの追加、 *User Folderの削除*、および*TraceFileComponent *の削除を推奨します。

1. （オプション）「カス **タム** 」を選択して、言語パッケージと、言語ファイルとプログラムファイルの場所を選択します。
1. ショートカットの場 **所を開始メニューで**&#x200B;選択

   ![](assets/6_4_workstation_wizard_folder.png)

   [開始 **メニューフォルダを作成しない]をクリックして** 、Windowsのメニューにショートカットをインストールしないようにします。

1. 「**次へ」をクリックします。** 選択したファイルの場所のパスと言語の概要が表示されます。 Click **Install.**

1. Data Workbenchの証 **明書を探します**。

   インストール中にData Workbenchの証明書が見つからない場合は、ダイアログが開いて証明書の場所(デフォルトではクライアントの **Certificates** フォルダーにある **.pem****** ファイル)を参照するか、「スキップ」をクリックしてインストール後の証明書を検索します。

   証明書を **見つけたら** 、「Install」をクリックします。

1. セットアップウィザードが完了し、Data Workbenchがインストールされたら、「完了」をクリ **ックし** 、セットアップを完了します。

   >[!NOTE]
   >
   >ワークステーションセットアップウィザードの既定のログの場所( **[!DNL C:\Users\)<userName>&#39;\AppData\Local\Temp ]**

   設定後にWorkbenchを **開くには** 、「アプリケーションを起動」チェックボックスを選択します。

1. **ファイル内のサーバ** ーへの接続を設定 **[!DNL Insight.cfg]** します。

   ワークステーションのインストール後、拡張ワークステーション設定ワークスペースが開き、 [Insight.cfg](/help/home/c-get-started/c-insght-config-param.md)** (Enhanced Workstation Configuration Experience)ファイルにサーバー接続情報を入力する方法や、ドロップダウンからプロファイルを選択するオプションに関する追加情報が表示されます。 サーバーへの接続状態を表示することもできます。

   ![](assets/6_4_workstation_install_conf_conn.png)

## インストールフォルダ {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Data Workbenchのフォルダー構造には、2つのインストール場所があります。

* **プログラムファイル****Insight.exe** 、およびサポートするクライアントファイル(**Insight.ini**)が、デフォルトで次の場所に配置されるようになりました。

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Appdataフ **ォルダ** 。

   **Insight.cfg**、プロファイル、証明書、トレースログおよびユーザーファイルは、デフォルトで次の場所に配置されるようになりました。

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   ファイル内の **Appdata** フォルダのパスを設定でき `Insight.ini` ます。

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## ワークステーションのアンインストール {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbenchには、ワークステーション（デフォルトでは）をアンインストールする実行可能ファイルが含まれるようにな **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**&#x200B;りました。

を起動し、Data Workbenchワークステーションファイルをハードドライブから削除する手順に従います。

>[!NOTE]
>
>開始メニューの「 **Uninstall Data Workbench****」ショートカットを使用するか、/からunins000.exe実行可能ファイルを起動で** きます **[!UICONTROL Control Panel]****[!UICONTROL Program and Features]**。
