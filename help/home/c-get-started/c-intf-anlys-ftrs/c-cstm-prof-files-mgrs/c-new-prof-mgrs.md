---
description: プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。
solution: Analytics
title: プロファイルマネージャーの作成
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# プロファイルマネージャーの作成{#create-a-profile-manager}

プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。

You may want to access a subdirectory of the [!DNL Profile Manager] without having to navigate its entire directory structure. For example, the [!DNL Metrics] and [!DNL Workspaces] menu options available on the [!DNL Manage] menu of the workspace window menu enable you to open the Profile Manager Metrics and Workspaces folders, respectively.

について詳しくは、プロファイルマ [!DNL Profile Manager]ネージャー [を参照してください](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

デフォルトでは、以下のマネージャーにアクセスできます。

* **[!DNL Metrics Manager]:**プロファイルマネージャーのMetricsフォルダーの内容を表示します。 各プロファイル内で定義された指標を開いたり、編集したり、削除したり、コピーしたりできます。
* **[!DNL Reports Manager]:**プロファイルマネージャーのReportsフォルダーの内容を表示します。 レポートのワークスペースまたは[!DNL report.cfg]ファイルを開いたり、編集したり、削除したり、コピーしたりできます。

* **[!DNL Workspaces Manager]:**プロファイルマネージャーのWorkspacesフォルダーの内容を表示します。 All of the files for configuring the[!DNL Worktop]’s tabs are located here. See[Customizing Worktop Tabs](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench enables you to create additional profile managers that display one subdirectory from the [!DNL Profile Manager]. Each manager that you create must have a [!DNL .vw] file that specifies the [!DNL Profile Manager] directory whose contents it shows and the properties of that window. You can use the [!DNL .vw] file for any of the provided managers as a template.

**プロファイルマネージャーを作成するには**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
1. Menu ディレクトリ内で、**[!UICONTROL Admin]** ディレクトリをクリックしてから、**[!UICONTROL Profile]** ディレクトリをクリックします。The [!DNL .vw] files for the existing managers are located here.
1. In the *profile name* column, right-click the check mark for the one of the [!DNL .vw] files (for example, [!DNL Workspaces.vw]), then click **[!UICONTROL Make Local]**.

   [!DNL User] 列にそのファイルのチェックマークが表示されます。

1. Right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. In the [!DNL Profile Path] field, type the [!DNL Profile Manager] directory for which you want to create a new manager. ディレクトリ名の後に必ずスラッシュ（/）を含めてください。

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

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the edited file to the *Data Workbench installation folder*\User\*working profile name*\Menu\Admin\Profile Management.

   Be sure to change the name of the [!DNL .vw] file to reflect the directory in the [!DNL Profile Manager] to which it corresponds.

1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

