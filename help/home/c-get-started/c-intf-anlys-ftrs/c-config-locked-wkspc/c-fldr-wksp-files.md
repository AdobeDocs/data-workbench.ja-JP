---
description: Data Workbenchインストールディレクトリの Workspaces フォルダ内で、folder.lock ファイルは特定のフォルダ内のワークスペースをロックするかどうかを指定し、workspace name.lock ファイルは特定のワークスペースをロックするかどうかを指定します。
title: Folder.lock ファイルと workspace name.lock ファイル
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 35%

---

# Folder.lock ファイルと workspace name.lock ファイル{#folder-lock-and-workspace-lock-files}

{{eol}}

Data Workbenchインストールディレクトリの Workspaces フォルダ内で、folder.lock ファイルは特定のフォルダ内のワークスペースをロックするかどうかを指定し、workspace name.lock ファイルは特定のワークスペースをロックするかどうかを指定します。

フォルダー全体をロックする場合、Workspaces フォルダーレベルまたはサブフォルダー（タブ）レベルでロックできます。すべてのフォルダーを（Workspaces フォルダーレベルで）ロックまたはロック解除してから、特定のサブフォルダー（[!DNL folder.lock] ファイルを使用）または特定のワークスペース（*workspace name*.lock ファイルを使用）に対して例外を指定することもできます。

次に、 [!DNL Profile Manager] は 3 つの要素をハイライトします。

* メインの Workspaces フォルダー用の [!DNL folder.lock] ファイル
* A [!DNL Monthly Numbers.lock] ファイル [!DNL Monthly Numbers.vw] ワークスペースファイル

* Workspaces\Custom サブフォルダー用の [!DNL folder.lock] ファイル

![](assets/wsp_Locking_lockFiles.png)

この例では、 [!DNL Workspaces folder.lock] ファイルが「ロック済み」に設定され、このData Workbenchのインスタンス内のすべてのワークスペースがロックされます。 Workspaces\ サブフォルダーの [!DNL folder.lock] ファイルは unlocked に設定されているため、「[!DNL Custom]カスタム」タブのすべてのワークスペースがロック解除されます。最後に、[!DNL Monthly Numbers.lock] ファイルが locked に設定されているため、Monthly Numbers ワークスペースはロックされます。

## .lock ファイルの作成 {#section-c4f78b4b43c347368a376904effb41d2}

次の項目を作成できます。 [!DNL new folder.lock] ファイルを [!DNL Create menu] オプション [!DNL Profile Manager] または [!DNL Workspaces Manager]. また、 [!DNL folder.lock] または *ワークスペース名*&#x200B;既存の [!DNL .lock] ファイルを適切なフォルダーに追加し、ファイル名を変更します ( *ワークスペース名*.lock ファイルのみ )、および必要に応じてファイル内の設定を変更します。

**新しい folder.lock ファイルを作成するには**

1. Data Workbenchで、 [!DNL Workspaces Manager] ワークスペース内で右クリックし、 **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. [!DNL folder.lock] ファイルを作成するフォルダーをクリックします。
1. 内 [!DNL User] 」列をクリックし、セル内を右クリックして、 **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] ファイルが表示されます。 [!DNL New folder.lock] ファイルは次のように設定されます。 [ロック解除] デフォルトでは。
1. （オプション）ファイル内の設定を変更する必要がある場合：

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. この [!DNL folder.lock] ファイルが開きます。

   1. 設定をに変更します。 [ロック済み].
   1. ファイルを保存して閉じます。

1. これを同じ作業プロファイルを使用するすべてのユーザーに対して設定するには、ファイルのチェックマークを右クリックし、 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

このフォルダー内のワークスペースが、新しいファイル内の設定に従ってロックまたはロック解除されます。

**既存のファイルから .lock ファイルを作成するには**

1. 内 [!DNL Profile Manager] または [!DNL Workspaces Manager]、既存の [!DNL .lock] ファイルを開き、 **[!UICONTROL Copy]**.
1. 内 [!DNL User] 」列を使用して、 [!DNL .lock] ファイルを開き、セル内で右クリックし、 **[!UICONTROL Paste]**.
1. このファイルを使用して個々のワークスペースをロックする場合は、 [!DNL .lock] ファイルを [!DNL User] 列の名前を変更し、 [!DNL File] フィールドを使用して、ロックするワークスペースの名前を指定します。

   例えば、 [!DNL Monthly Numbers.vw] ワークスペースで、「 [!DNL Monthly Numbers.lock].&quot;このファイルを使用して個々のワークスペースをロックする場合は、 [!DNL .lock] ファイルを [!DNL User] 列の名前を変更し、 [!DNL File] フィールドを使用して、ロックするワークスペースの名前を指定します。 例えば、 [!DNL Monthly Numbers.vw] ワークスペースで、「 [!DNL Monthly Numbers.lock].&quot;

1. ファイル内の設定を変更するには、次のようにします。

   1. ファイルのチェックマークを右クリックします。
   1. クリック **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. この [!DNL .lock] ファイルが開きます。

   1. 設定をに変更します。 [ロック済み] または [ロック解除].
   1. ファイルを保存して閉じます。

1. これを同じ作業プロファイルを使用するすべてのユーザーに対して設定するには、ファイルのチェックマークを右クリックし、 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

新しいファイル内の設定に従って、選択したワークスペースがロックまたはロック解除されます。
