---
description: デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。
solution: Analytics
title: ワークスペースの保存
topic: Data workbench
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークスペースの保存{#save-a-workspace}

デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。

ワークスペースがサーバーワークスペースの場合、更新したワークスペースをData Workbenchサーバーに特別に保存しない限り、変更はローカルにのみ保存されます。 ロックされたワークスペースについて詳しくは、「ワークスペースのロ [ック解除」を参照してくださ](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)い。

## ワークスペースのローカル保存 {#section-3f331c880f1a490c96844103c2432d61}

The default save location is the **User\profile name\Workspaces\tab name** folder within the Data Workbench installation directory. For example, if you are working with the Movies profile and you save a workspace locally from the [!UICONTROL Custom] tab, the workspace is saved to the **User\Movies\Workspaces\Custom** folder in your Data Workbench installation directory.

**ワークスペースに対する変更を保存するには**

* In the workspace, click **[!UICONTROL File]**, then **[!UICONTROL Save]**.

**既存のワークスペースを新しいワークスペースとして保存するには**

1. On the desired [!DNL Worktop] tab, click the thumbnail of the workspace you want to display.
1. ワークスペースでをクリックし、 **[!UICONTROL File]**&#x200B;をクリックしてからをクリックしま **[!UICONTROL Save Copy As]**&#x200B;す。
1. In the [!DNL Save Workspace As] dialog box, specify the name and location where you want to save the copied workspace and click **[!UICONTROL Save]**.

## Save a workspace to the Data Workbench server {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>適切な権限を持つユーザーのみが、Data Workbenchサーバーにワークスペースを保存できます。 詳細については、システム管理者にお問い合わせください。

接続されたData Workbenchサーバーにワークスペースを保存することは、ワークスペースの発行とも呼ばれます。これは、他のユーザーがワークスペースを使用できるようにするためです。 By default, workspaces are saved to the *working profile name*\Workspaces\*tab name* folder of the Data Workbench server. For example, if you are working with the Movies profile and you save a workspace to the connected Data Workbench server from the [!DNL Custom] tab, the workspace is saved to the Movies\Workspaces\Custom folder of the Data Workbench server.

**ワークスペースをData Workbenchサーバーに保存するには**

* On the desired [!DNL Worktop] tab, right-click the thumbnail of the workspace that you want to save to the Data Workbench server and click **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
