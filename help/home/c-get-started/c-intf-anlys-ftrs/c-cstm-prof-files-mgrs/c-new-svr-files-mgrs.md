---
description: サーバーファイルマネージャーには、Data Workbenchサーバーのインストールディレクトリ内の、設定ファイルや参照ファイルを含むすべてのディレクトリが表示されます。
solution: Analytics
title: サーバーファイルマネージャーの作成
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# サーバーファイルマネージャーの作成{#create-a-server-files-manager}

サーバーファイルマネージャーには、Data Workbenchサーバーのインストールディレクトリ内の、設定ファイルや参照ファイルを含むすべてのディレクトリが表示されます。

You may want to access a portion of the [!DNL Server Files Manager] without having to navigate its entire directory structure or display only a few of the subdirectories to address a particular need. For example, you might want to create a separate [!DNL Server Files Manager] that displays only the Access Control and Users subdirectories, enabling you to manage your users and their access.

Each manager that you create must have a [!DNL .vw] file. You can use the [!DNL Server Files.vw] file as a template.

サーバーファイルマネージャ [!DNL Server Files Manager]ーの詳細 [については、を参照してください](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**サーバーファイルマネージャーを作成するには**

1. で、ディレ [!DNL Profile Manager]クトリをクリ **[!UICONTROL Menu]** ックし、次にディレクトリをクリッ **[!UICONTROL Admin]** クします。 The [!DNL Server Files.vw] file is located here.
1. In the *profile name* column, right-click the check mark for the [!DNL Server Files.vw] file and click **[!UICONTROL Make Local]**. [!DNL User] 列にそのファイルのチェックマークが表示されます。
1. Right-click the check mark for the [!DNL Server Files.vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Server Files.vw] file opens.
1. ディレクトリを削除するには、の上の枠を右クリックし、// [!DNL Server Files Manager] &lt; **[!UICONTROL Server Directories]** >をクリックし **[!UICONTROL Remove]** ます ***[!UICONTROL directory name]***。
1. ディレクトリを追加するには、の上の枠を右クリックし、// [!DNL Server Files Manager]をク **[!UICONTROL Server Directories]** リック **[!UICONTROL Add]** します **[!UICONTROL Directory]**。

   ディレクトリの URI を「URI」フィールドに入力し、「**[!UICONTROL OK]**」をクリックします。

   >[!NOTE]
   >
   >「URI」フィールドで複数のディレクトリを指定できます。 例えば、[!DNL Profiles\Marketing\]と入力した場合、サーバーファイルマネージャーにはMarketingサブディレクトリが含まれますが、Profilesディレクトリ内の他のサブディレクトリは含まれません。

1. の上の枠を右クリックし、をクリ [!DNL Server Files Manager] ックします **[!UICONTROL Save]**。
1. To create a new manager, change the file name in the [!DNL File Name] field, then click **[!UICONTROL Save]**. To overwrite the existing manager, click **[!UICONTROL Save]**.
1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column.

   Then, click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

