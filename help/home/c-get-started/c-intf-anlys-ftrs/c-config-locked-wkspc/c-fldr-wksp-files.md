---
description: Data WorkbenchインストールディレクトリのWorkspacesフォルダー内のfolder.lockファイルでは、特定のフォルダー内のワークスペースをロックするかどうかを指定し、workspace name.lockファイルでは、特定のワークスペースをロックするかどうかを指定します。
title: Folder.lock ファイルと workspace name.lock ファイル
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 35%

---

# Folder.lock ファイルと workspace name.lock ファイル{#folder-lock-and-workspace-lock-files}

Data WorkbenchインストールディレクトリのWorkspacesフォルダー内のfolder.lockファイルでは、特定のフォルダー内のワークスペースをロックするかどうかを指定し、workspace name.lockファイルでは、特定のワークスペースをロックするかどうかを指定します。

フォルダー全体をロックする場合、Workspaces フォルダーレベルまたはサブフォルダー（タブ）レベルでロックできます。すべてのフォルダーを（Workspaces フォルダーレベルで）ロックまたはロック解除してから、特定のサブフォルダー（[!DNL folder.lock] ファイルを使用）または特定のワークスペース（*workspace name*.lock ファイルを使用）に対して例外を指定することもできます。

次の[!DNL Profile Manager]の例では、3つの要素がハイライトされています。

* メインの Workspaces フォルダー用の [!DNL folder.lock] ファイル
* [!DNL Monthly Numbers.vw]ワークスペースファイルの[!DNL Monthly Numbers.lock]ファイル

* Workspaces\Custom サブフォルダー用の [!DNL folder.lock] ファイル

![](assets/wsp_Locking_lockFiles.png)

この例では、[!DNL Workspaces folder.lock]ファイルがlockedに設定され、このData Workbenchインスタンス内のすべてのワークスペースがロックされます。 Workspaces\ サブフォルダーの [!DNL folder.lock] ファイルは unlocked に設定されているため、「[!DNL Custom]カスタム」タブのすべてのワークスペースがロック解除されます。最後に、[!DNL Monthly Numbers.lock] ファイルが locked に設定されているため、Monthly Numbers ワークスペースはロックされます。

## .lock ファイルの作成{#section-c4f78b4b43c347368a376904effb41d2}

[!DNL Profile Manager]または[!DNL Workspaces Manager]の[!DNL Create menu]オプションを使用して、[!DNL new folder.lock]ファイルを作成できます。 また、既存の[!DNL .lock]ファイルを適切なフォルダーにコピー&amp;ペーストし、ファイル名を変更（*workspace name*.lockファイルのみ）し、必要に応じてファイル内の設定を変更することで、[!DNL folder.lock]または&#x200B;*workspace name*.lockファイルを作成できます。

**新しい folder.lock ファイルを作成するには**

1. Data Workbenchで、ワークスペース内で右クリックし、**[!UICONTROL Manage]**/**[!UICONTROL Profile]**/**[!UICONTROL Workspaces Manager]**&#x200B;をクリックして、[!DNL Workspaces Manager]を開きます。
1. [!DNL folder.lock] ファイルを作成するフォルダーをクリックします。
1. そのフォルダーの[!DNL User]列で、セル内を右クリックし、**[!UICONTROL Create]**/**[!UICONTROL folder.lock]**&#x200B;をクリックします。 [!DNL new folder.lock]ファイルが表示されます。 [!DNL New folder.lock] ファイルは、デフォルトでは [] unlockedに設定されています。
1. （オプション）ファイル内の設定を変更する必要がある場合：

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. [!DNL folder.lock]ファイルが開きます。

   1. 設定を[locked]に変更します。
   1. ファイルを保存して閉じます。

1. この設定を同じ作業プロファイルで作業しているすべてのユーザーに対して設定するには、ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]***&#x200B;をクリックします。

このフォルダー内のワークスペースが、新しいファイル内の設定に従ってロックまたはロック解除されます。

**既存のファイルから .lock ファイルを作成するには**

1. [!DNL Profile Manager]または[!DNL Workspaces Manager]で、既存の[!DNL .lock]ファイルのチェックマークを右クリックし、**[!UICONTROL Copy]**&#x200B;をクリックします。
1. [!DNL .lock]ファイルを貼り付けるフォルダーの[!DNL User]列で、セル内を右クリックし、**[!UICONTROL Paste]**&#x200B;をクリックします。
1. このファイルを使用して個々のワークスペースをロックする場合は、[!DNL User]列の[!DNL .lock]ファイルのチェックマークを右クリックし、[!DNL File]フィールドの名前をロックするワークスペースの名前に合わせて変更します。

   例えば、[!DNL Monthly Numbers.vw]ワークスペースをロックするには、ファイルに「[!DNL Monthly Numbers.lock]」という名前を付けます。このファイルを使用して個々のワークスペースをロックする場合は、[!DNL User]列の[!DNL .lock]ファイルのチェックマークを右クリックし、[!DNL File]フィールドの名前をロックするワークスペースの名前に合わせて変更します。 例えば、[!DNL Monthly Numbers.vw]ワークスペースをロックするには、ファイルに「[!DNL Monthly Numbers.lock]」という名前を付けます。

1. ファイル内の設定を変更するには、次のようにします。

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. [!DNL .lock]ファイルが開きます。

   1. 設定を[locked]または[unlocked]に変更します。
   1. ファイルを保存して閉じます。

1. この設定を同じ作業プロファイルで作業しているすべてのユーザーに対して設定するには、ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL working profile name]***&#x200B;をクリックします。

新しいファイル内の設定に従って、選択したワークスペースがロックまたはロック解除されます。
