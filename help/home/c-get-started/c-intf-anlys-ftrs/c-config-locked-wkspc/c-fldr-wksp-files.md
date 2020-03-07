---
description: Data WorkbenchインストールディレクトリのWorkspacesフォルダー内にあるfolder.lockファイルは、特定のフォルダー内のワークスペースをロックするかどうかを指定し、workspace name.lockファイルは特定のワークスペースをロックするかどうかを指定します。
solution: Analytics
title: Folder.lockファイルとworkspace.lockファイル
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Folder.lock and workspace.lock files{#folder-lock-and-workspace-lock-files}

Data WorkbenchインストールディレクトリのWorkspacesフォルダー内にあるfolder.lockファイルは、特定のフォルダー内のワークスペースをロックするかどうかを指定し、workspace name.lockファイルは特定のワークスペースをロックするかどうかを指定します。

フォルダー全体をロックする場合、Workspaces フォルダーレベルまたはサブフォルダー（タブ）レベルでロックできます。すべてのフォルダーを（Workspaces フォルダーレベルで）ロックまたはロック解除してから、特定のサブフォルダー（[!DNL folder.lock] ファイルを使用）または特定のワークスペース（*workspace name*.lock ファイルを使用）に対して例外を指定することもできます。

The following example of the [!DNL Profile Manager] highlights three elements:

* メインの Workspaces フォルダー用の [!DNL folder.lock] ファイル
* A [!DNL Monthly Numbers.lock] file for the [!DNL Monthly Numbers.vw] workspace file

* Workspaces\Custom サブフォルダー用の [!DNL folder.lock] ファイル

![](assets/wsp_Locking_lockFiles.png)

In this example, the [!DNL Workspaces folder.lock] file is set to locked, which locks all of the workspaces in this instance of Data Workbench. Workspaces\ サブフォルダーの [!DNL folder.lock] ファイルは unlocked に設定されているため、「[!DNL Custom]カスタム」タブのすべてのワークスペースがロック解除されます。最後に、[!DNL Monthly Numbers.lock] ファイルが locked に設定されているため、Monthly Numbers ワークスペースはロックされます。

## .lock ファイルの作成{#section-c4f78b4b43c347368a376904effb41d2}

またはのオプション [!DNL new folder.lock] を使用して [!DNL Create menu] ファイルを作成 [!DNL Profile Manager] できます [!DNL Workspaces Manager]。 You also can create a [!DNL folder.lock] or *workspace name*.lock file by copying and pasting an existing [!DNL .lock] file to the appropriate folder, changing the name of the file (for *workspace name*.lock files only), and changing the setting in the file if necessary.

**新しい folder.lock ファイルを作成するには**

1. Data Workbenchで、ワークスペース内で右ク [!DNL Workspaces Manager] リックし、//をクリックして、を **[!UICONTROL Manage]** 開き **[!UICONTROL Profile]** ます **[!UICONTROL Workspaces Manager]**。
1. [!DNL folder.lock] ファイルを作成するフォルダーをクリックします。
1. In the [!DNL User] column for that folder, right-click in the cell and click **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. ファイル [!DNL new folder.lock] が表示されます。 [!DNL New folder.lock] ファイルはデフォルトでロッ [ク解除] されます。
1. （オプション）ファイル内の設定を変更する必要がある場合：

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL folder.lock] file opens.

   1. Change the setting to [locked].
   1. ファイルを保存して閉じます。

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

このフォルダー内のワークスペースが、新しいファイル内の設定に従ってロックまたはロック解除されます。

**既存のファイルから .lock ファイルを作成するには**

1. またはで、 [!DNL Profile Manager] 既存の [!DNL Workspaces Manager]ファイルのチェックマークを右クリックし、を [!DNL .lock] クリックしま **[!UICONTROL Copy]**&#x200B;す。
1. In the [!DNL User] column for the folder into which you want to paste the [!DNL .lock] file, right-click in the cell and click **[!UICONTROL Paste]**.
1. If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock.

   For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].”If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock. For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].”

1. ファイル内の設定を変更するには、次のようにします。

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL .lock] file opens.

   1. Change the setting to [locked] or [unlocked].
   1. ファイルを保存して閉じます。

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

新しいファイル内の設定に従って、選択したワークスペースがロックまたはロック解除されます。
