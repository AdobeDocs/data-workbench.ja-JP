---
description: プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。
title: プロファイルマネージャーの作成
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 25%

---

# プロファイルマネージャーの作成{#create-a-profile-manager}

{{eol}}

プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。

サブディレクトリ ( [!DNL Profile Manager] ディレクトリ構造全体をナビゲートする必要がなくなりました。 例えば、 [!DNL Metrics] および [!DNL Workspaces] メニューオプション [!DNL Manage] ワークスペースウィンドウメニューのメニューを使用して、プロファイルマネージャーの Metrics フォルダーと Workspaces フォルダーをそれぞれ開くことができます。

詳しくは、 [!DNL Profile Manager]を参照してください。 [プロファイルマネージャー](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

デフォルトでは、以下のマネージャーにアクセスできます。

* **[!DNL Metrics Manager]:** プロファイルマネージャーの Metrics フォルダーの内容を表示します。 各プロファイル内で定義された指標を開いたり、編集したり、削除したり、コピーしたりできます。
* **[!DNL Reports Manager]:** プロファイルマネージャーの Reports フォルダーの内容を表示します。 レポートのワークスペースまたは [!DNL report.cfg] ファイルを開いたり、編集したり、削除したり、コピーしたりできます。

* **[!DNL Workspaces Manager]:** プロファイルマネージャーの Workspaces フォルダーの内容を表示します。 設定用のすべてのファイル [!DNL Worktop]のタブはここにあります。 詳しくは、 [ワークトップタブのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbenchを使用すると、追加のプロファイルマネージャーを作成して、 [!DNL Profile Manager]. 作成する各マネージャーには、 [!DNL .vw] 指定したファイル [!DNL Profile Manager] 表示する内容とそのウィンドウのプロパティを含むディレクトリ。 以下を使用して、 [!DNL .vw] ファイルを作成します。

**プロファイルマネージャーを作成するには**

1. 内 [!DNL Profile Manager]、 **[!UICONTROL Menu]** ディレクトリの内容を表示します。
1. Menu ディレクトリ内で、**[!UICONTROL Admin]** ディレクトリをクリックしてから、**[!UICONTROL Profile]** ディレクトリをクリックします。この [!DNL .vw] 既存のマネージャ用のファイルは、ここにあります。
1. 内 *プロファイル名* 列で、 [!DNL .vw] ファイル ( 例： [!DNL Workspaces.vw]) をクリックしてから、 **[!UICONTROL Make Local]**.

   [!DNL User] 列にそのファイルのチェックマークが表示されます。

1. のチェックマークを右クリックします。 [!DNL .vw] ファイルを [!DNL User] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 内 [!DNL Profile Path] フィールドに、 [!DNL Profile Manager] 新しいマネージャを作成するディレクトリ。 ディレクトリ名の後に必ずスラッシュ（/）を含めてください。

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. メモ帳で、 **[!UICONTROL File]** > **[!UICONTROL Save As]** 編集したファイルを *Data Workbenchインストールフォルダー*\User\*working profile name*\Menu\Admin\Profile Management.

   必ず [!DNL .vw] ディレクトリを [!DNL Profile Manager] 対応する

1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、 [!DNL .vw] ファイルを [!DNL User] 列とクリック **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
