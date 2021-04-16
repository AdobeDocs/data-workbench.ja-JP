---
description: デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。
title: ワークスペースの保存
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 17%

---

# ワークスペースの保存{#save-a-workspace}

デフォルトでは、ロック解除されたワークスペースを閉じると、ワークスペースに対して行った変更はすべて保存されます。

ワークスペースがサーバーワークスペースの場合、更新したワークスペースをData Workbenchサーバーに特に保存しない限り、変更はローカルにのみ保存されます。 ロックされたワークスペースについて詳しくは、「[ワークスペースのロック解除](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)」を参照してください。

## ワークスペースをローカルに保存{#section-3f331c880f1a490c96844103c2432d61}

デフォルトの保存場所は、Data Workbenchのインストールディレクトリ内の&#x200B;**User\プロファイルname\Workspaces\tab name**&#x200B;フォルダーです。 例えば、Moviesプロファイルーで作業している場合に、「[!UICONTROL Custom]」タブからワークスペースをローカルに保存すると、ワークスペースはData Workbenchーのインストールディレクトリ内の&#x200B;**User\Movies\Workspaces\Custom**&#x200B;フォルダーに保存されます。

**ワークスペースに対する変更を保存するには**

* ワークスペースで、「**[!UICONTROL File]**」、「**[!UICONTROL Save]**」の順にクリックします。

**既存のワークスペースを新しいワークスペースとして保存するには**

1. 目的の[!DNL Worktop]タブで、表示するワークスペースのサムネールをクリックします。
1. ワークスペースで、「**[!UICONTROL File]**」、「**[!UICONTROL Save Copy As]**」の順にクリックします。
1. [!DNL Save Workspace As]ダイアログボックスで、コピーしたワークスペースを保存する名前と場所を指定し、「**[!UICONTROL Save]**」をクリックします。

## ワークスペースをData Workbenchサーバーに保存{#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>適切な権限を持つユーザーのみが、ワークスペースをData Workbenchサーバーに保存できます。 詳細については、システム管理者にお問い合わせください。

接続されているData Workbenchサーバーにワークスペースを保存することは、ワークスペースの発行とも呼ばれます。これにより、他のユーザーがワークスペースを利用できるようになるからです。 デフォルトでは、ワークスペースはData Workbenchサーバーの&#x200B;*作業プロファイル名*\Workspaces\*tab name*フォルダーに保存されます。 例えば、Moviesプロファイルーで作業している場合、接続されているData Workbenchサーバーに「[!DNL Custom]」タブからワークスペースを保存すると、ワークスペースはMovies\Workspaces\Custom folder of the Data Workbench serverフォルダーに保存されます。

**ワークスペースをData Workbenchサーバーに保存するには**

* 目的の[!DNL Worktop]タブで、Data Workbenchサーバーに保存するワークスペースのサムネールを右クリックし、「**[!UICONTROL Save to server]**」をクリックします。

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
