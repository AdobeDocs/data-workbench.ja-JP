---
description: デフォルトでは、新たに作成されたタブには、関連付けられたディレクトリ内にあるサブフォルダーが、サブタブではなく階層化されたドロップダウンサブディレクトリとして表示されます。
title: サブフォルダーのサブタブ表示
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 26%

---

# サブフォルダーのサブタブ表示{#display-subfolders-as-subtabs}

{{eol}}

デフォルトでは、新たに作成されたタブには、関連付けられたディレクトリ内にあるサブフォルダーが、サブタブではなく階層化されたドロップダウンサブディレクトリとして表示されます。

サブフォルダーをサブタブとして（次の例のように）表示するには、 [!DNL empty folder.useTabs] ファイルを *作業プロファイル名*\Workspaces\*tab name folder* (Data Workbenchのインストールディレクトリ内 )

次の例は、 [!DNL Custom] タブにドロップダウンサブディレクトリが追加されました。

![](assets/client-sub.png)

次の場合、 [!DNL empty folder.useTabs] Workspaces\Custom フォルダ内のファイルを選択すると、Custom フォルダ内のすべてのサブフォルダが [!DNL Worktop] をサブタブとして使用します。次の例を参照してください。

![](assets/client-sub2.png)

**サブフォルダーをサブタブとして[!DNL Worktop]**

>[!NOTE]
>
>各ディレクトリレベルには、 [!DNL Tab Name.useTabs] サブフォルダーのコンテンツを、階層的なドロップダウンサブディレクトリではなくサブタブとして表示するためのファイル。

1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Workspaces]** をクリックして、その内容を表示します。
1. 内 *作業プロファイル名* 列で、次のいずれかのチェックマークを右クリックします。 [!DNL folder.useTabs] ファイルとクリック **[!UICONTROL Copy]**.
1. を右クリックします。 [!DNL User] 列を開き、 **[!UICONTROL Paste]**. そのタブ内のサブフォルダーが、サブタブとして表示されるようになります。
1. （オプション）作業プロファイルのすべてのユーザーがこの変更を利用できるようにするには、 [!DNL new folder.useTabs] ファイルを [!DNL User] 列とクリック **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.
