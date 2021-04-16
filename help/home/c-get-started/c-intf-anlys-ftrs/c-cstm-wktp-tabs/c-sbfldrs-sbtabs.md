---
description: デフォルトでは、新たに作成されたタブには、関連付けられたディレクトリ内にあるサブフォルダーが、サブタブではなく階層化されたドロップダウンサブディレクトリとして表示されます。
title: サブフォルダーのサブタブ表示
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 26%

---

# サブフォルダーのサブタブ表示{#display-subfolders-as-subtabs}

デフォルトでは、新たに作成されたタブには、関連付けられたディレクトリ内にあるサブフォルダーが、サブタブではなく階層化されたドロップダウンサブディレクトリとして表示されます。

サブフォルダーをサブタブとして（次の例に示すように）表示するには、Data Workbenchーインストールディレクトリ内の&#x200B;*workingプロファイルー名*\Workspaces\*tab name folder*に[!DNL empty folder.useTabs]ファイルを配置します。

次の例は、ドロップダウンサブディレクトリを含む[!DNL Custom]タブを示しています。

![](assets/client-sub.png)

[!DNL empty folder.useTabs]ファイルをWorkspaces\Customフォルダーに配置すると、次の例に示すように、Customフォルダー内のすべてのサブフォルダーが[!DNL Worktop]にサブタブとして表示されます。

![](assets/client-sub2.png)

**サブフォルダーを[!DNL Worktop]**

>[!NOTE]
>
>各ディレクトリレベルには、サブフォルダーのコンテンツを階層化されたドロップダウンサブディレクトリではなくサブタブとして表示するための[!DNL Tab Name.useTabs]ファイルが必要です。

1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Workspaces]**&#x200B;をクリックして、内容を表示します。
1. *作業プロファイル名*&#x200B;列で、[!DNL folder.useTabs]ファイルの1つのチェックマークを右クリックし、**[!UICONTROL Copy]**&#x200B;をクリックします。
1. Workspaces\*tab name*フォルダーの[!DNL User]列内で右クリックし、**[!UICONTROL Paste]**&#x200B;をクリックします。 そのタブ内のサブフォルダーが、サブタブとして表示されるようになります。
1. （オプション）作業プロファイルのすべてのユーザーがこの変更を利用できるようにするには、[!DNL User]列の[!DNL new folder.useTabs]ファイルの白いチェックマークを右クリックし、**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**&#x200B;をクリックします。
