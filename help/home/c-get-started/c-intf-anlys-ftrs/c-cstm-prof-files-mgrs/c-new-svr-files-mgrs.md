---
description: サーバーファイルマネージャーには、設定ファイルや参照ファイルを含む、Data Workbenchサーバーインストールディレクトリ内のすべてのディレクトリが表示されます。
title: サーバーファイルマネージャーの作成
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 9%

---

# サーバーファイルマネージャーの作成{#create-a-server-files-manager}

{{eol}}

サーバーファイルマネージャーには、設定ファイルや参照ファイルを含む、Data Workbenchサーバーインストールディレクトリ内のすべてのディレクトリが表示されます。

以下の [!DNL Server Files Manager] 特定のニーズに対処するために、ディレクトリ構造全体を移動したり、いくつかのサブディレクトリのみを表示したりする必要はありません。 例えば、 [!DNL Server Files Manager] には、 Access Control サブディレクトリと Users サブディレクトリのみが表示され、ユーザーとそのアクセス権を管理できます。

作成する各マネージャーには、 [!DNL .vw] ファイル。 以下を使用して、 [!DNL Server Files.vw] ファイルをテンプレートとして使用します。

詳しくは、 [!DNL Server Files Manager]を参照してください。 [サーバーファイルマネージャー](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**サーバーファイルマネージャを作成するには**

1. 内 [!DNL Profile Manager]、 **[!UICONTROL Menu]** ディレクトリ、 **[!UICONTROL Admin]** ディレクトリ。 この [!DNL Server Files.vw] ファイルはここに配置されています。
1. 内 *プロファイル名* 列で、 [!DNL Server Files.vw] ファイルを開き、 **[!UICONTROL Make Local]**. [!DNL User] 列にそのファイルのチェックマークが表示されます。
1. のチェックマークを右クリックします。 [!DNL Server Files.vw] ファイルを [!DNL User] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. この [!DNL Server Files.vw] ファイルが開きます。
1. ディレクトリを削除するには、 [!DNL Server Files Manager] をクリックし、 **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. ディレクトリを追加するには、 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   ディレクトリの URI を「URI」フィールドに入力し、「**[!UICONTROL OK]**」をクリックします。

   >[!NOTE]
   >
   >「URI」フィールドに複数のディレクトリを指定できます。 例えば、 [!DNL Profiles\Marketing\]サーバーファイルマネージャーには Marketing サブディレクトリが含まれますが、Profiles ディレクトリ内の他のサブディレクトリは含まれません。

1. 右クリックし、 [!DNL Server Files Manager] をクリックし、 **[!UICONTROL Save]**.
1. 新しいマネージャを作成するには、 [!DNL File Name] 「 」フィールドで、「 **[!UICONTROL Save]**. 既存のマネージャを上書きするには、 **[!UICONTROL Save]**.
1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、 [!DNL .vw] ファイルを [!DNL User] 列。

   次に、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
