---
description: サーバーファイルマネージャーには、設定ファイルや参照ファイルなど、Data Workbenchサーバーのインストールディレクトリにあるすべてのディレクトリが表示されます。
title: サーバーファイルマネージャーの作成
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 9%

---

# サーバーファイルマネージャーの作成{#create-a-server-files-manager}

サーバーファイルマネージャーには、設定ファイルや参照ファイルなど、Data Workbenchサーバーのインストールディレクトリにあるすべてのディレクトリが表示されます。

ディレクトリ構造全体を移動する必要なく[!DNL Server Files Manager]の一部にアクセスしたり、特定のニーズに対応するために一部のサブディレクトリのみを表示したりできます。 例えば、アクセス制御とUsersサブディレクトリのみを表示する個別の[!DNL Server Files Manager]を作成して、ユーザーとそのアクセスを管理できるようにします。

作成する各マネージャには[!DNL .vw]ファイルが必要です。 [!DNL Server Files.vw]ファイルをテンプレートとして使用できます。

[!DNL Server Files Manager]について詳しくは、[サーバーファイルマネージャー](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)を参照してください。

**サーバーファイルマネージャーを作成するには**

1. [!DNL Profile Manager]で、**[!UICONTROL Menu]**&#x200B;ディレクトリ、**[!UICONTROL Admin]**&#x200B;ディレクトリの順にクリックします。 [!DNL Server Files.vw]ファイルはここにあります。
1. *プロファイル名*&#x200B;列で、[!DNL Server Files.vw]ファイルのチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL User] 列にそのファイルのチェックマークが表示されます。
1. [!DNL User]列の[!DNL Server Files.vw]ファイルのチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。 [!DNL Server Files.vw]ファイルが開きます。
1. ディレクトリを削除するには、[!DNL Server Files Manager]の上の枠を右クリックし、**[!UICONTROL Server Directories]**/**[!UICONTROL Remove]**/***[!UICONTROL directory name]**>*&#x200B;をクリックします。
1. ディレクトリを追加するには、[!DNL Server Files Manager]の上の枠を右クリックし、**[!UICONTROL Server Directories]**/**[!UICONTROL Add]**/**[!UICONTROL Directory]**&#x200B;をクリックします。

   ディレクトリの URI を「URI」フィールドに入力し、「**[!UICONTROL OK]**」をクリックします。

   >[!NOTE]
   >
   >「URI」フィールドには複数のディレクトリを指定できます。 例えば、 [!DNL Profiles\Marketing\]と入力した場合、サーバーファイルマネージャーにはMarketingサブプロファイルが含まれますが、サーバーディレクトリ内のその他のサブディレクトリは含まれません。

1. [!DNL Server Files Manager]の上の枠を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
1. 新しいマネージャを作成するには、[!DNL File Name]フィールドのファイル名を変更し、**[!UICONTROL Save]**&#x200B;をクリックします。 既存のマネージャを上書きするには、**[!UICONTROL Save]**&#x200B;をクリックします。
1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、[!DNL User]列の[!DNL .vw]ファイルのチェックマークを右クリックします。

   次に、**[!UICONTROL Save to]**/*&lt;**[!UICONTROL working profile name]**>*&#x200B;をクリックします。
