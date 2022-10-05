---
description: デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。
title: ワークスペースの保存
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 17%

---

# ワークスペースの保存{#save-a-workspace}

{{eol}}

デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。

ワークスペースがサーバーワークスペースの場合、更新したワークスペースをサーバーに特に保存しない限り、変更はローカルでのみData Workbenchされます。 ロックされたワークスペースの詳細については、 [ワークスペースのロック解除](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## ワークスペースのローカル保存 {#section-3f331c880f1a490c96844103c2432d61}

デフォルトの保存場所は、 **ユーザー\プロファイル名\Workspaces\タブ名** フォルダーのインストールData Workbenchディレクトリ内のフォルダー。 例えば、Movies プロファイルを使用している場合、ワークスペースを [!UICONTROL Custom] 」タブをクリックした場合、ワークスペースは **User\Movies\Workspaces\Custom** フォルダーをData Workbenchのインストールディレクトリに保存します。

**ワークスペースに対する変更を保存するには**

* ワークスペースで、 **[!UICONTROL File]**&#x200B;を、 **[!UICONTROL Save]**.

**既存のワークスペースを新しいワークスペースとして保存するには**

1. 目的の [!DNL Worktop] 「 」タブで、表示するワークスペースのサムネールをクリックします。
1. ワークスペースで、 **[!UICONTROL File]**&#x200B;を選択し、「 **[!UICONTROL Save Copy As]**.
1. 内 [!DNL Save Workspace As] ダイアログボックスで、コピーしたワークスペースを保存する名前と場所を指定し、 **[!UICONTROL Save]**.

## ワークスペースをData Workbench・サーバに保存 {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>適切な権限を持つユーザーのみがワークスペースをData Workbench・サーバに保存できます。 詳細については、システム管理者にお問い合わせください。

接続されているData Workbenchサーバーへのワークスペースの保存は、他のユーザーがワークスペースを使用できるようにするので、ワークスペースの公開とも呼ばれます。 デフォルトでは、ワークスペースは *作業プロファイル名*\Workspaces\*tab name*Data Workbench 例えば、Movies プロファイルを使用している場合、ワークスペースを [!DNL Custom] 「 」タブに設定すると、ワークスペースは Movies サーバーの Movies\Workspaces\CustomData Workbenchーに保存されます。

**ワークスペースをData Workbench・サーバに保存するには**

* 目的の [!DNL Worktop] タブで、Data Workbench・サーバに保存するワークスペースのサムネールを右クリックし、 **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
