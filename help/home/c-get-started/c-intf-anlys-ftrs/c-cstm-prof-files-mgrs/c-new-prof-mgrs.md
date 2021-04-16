---
description: プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。
title: プロファイルマネージャーの作成
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 25%

---

# プロファイルマネージャーの作成{#create-a-profile-manager}

プロファイルマネージャーには、作業プロファイルに関連付けられたすべてのディレクトリが表示されます。

ディレクトリ構造全体をナビゲートすることなく、[!DNL Profile Manager]のサブディレクトリにアクセスしたい場合があります。 例えば、ワークスペースウィンドウメニューの[!DNL Manage]メニューで使用できる[!DNL Metrics]と[!DNL Workspaces]のメニューオプションを使用すると、それぞれプロファイルマネージャーの指標フォルダーとWorkspacesフォルダーを開くことができます。

[!DNL Profile Manager]について詳しくは、[プロファイルマネージャ](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)を参照してください。

デフォルトでは、以下のマネージャーにアクセスできます。

* **[!DNL Metrics Manager]:** プロファイルマネージャのMetricsフォルダの内容を表示します。各プロファイル内で定義された指標を開いたり、編集したり、削除したり、コピーしたりできます。
* **[!DNL Reports Manager]:** プロファイルマネージャのReportsフォルダの内容を表示します。レポートのワークスペースまたは [!DNL report.cfg] ファイルを開いたり、編集したり、削除したり、コピーしたりできます。

* **[!DNL Workspaces Manager]:** プロファイルマネージャのWorkspacesフォルダの内容を表示します。[!DNL Worktop]のタブを設定するためのファイルは、すべてここにあります。 「[ワークトップタブのカスタマイズ](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)」を参照してください。

Data Workbenchを使用すると、[!DNL Profile Manager]の1つのサブディレクトリを表示する追加のプロファイルマネージャーを作成できます。 作成する各マネージャには、その内容を表示する[!DNL Profile Manager]ディレクトリとそのウィンドウのプロパティを指定する[!DNL .vw]ファイルが必要です。 指定されたマネージャーの[!DNL .vw]ファイルは、テンプレートとして使用できます。

**プロファイルマネージャーを作成するには**

1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Menu]**&#x200B;ディレクトリをクリックして、その内容を表示します。
1. Menu ディレクトリ内で、**[!UICONTROL Admin]** ディレクトリをクリックしてから、**[!UICONTROL Profile]** ディレクトリをクリックします。既存のマネージャー用の[!DNL .vw]ファイルは、ここにあります。
1. *プロファイル名*&#x200B;列で、[!DNL .vw]ファイルの1つ（例：[!DNL Workspaces.vw]）のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。

   [!DNL User] 列にそのファイルのチェックマークが表示されます。

1. [!DNL User]列の[!DNL .vw]ファイルのチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Notepad]**&#x200B;をクリックします。
1. [!DNL Profile Path]フィールドに、新しいマネージャーを作成する[!DNL Profile Manager]ディレクトリを入力します。 ディレクトリ名の後に必ずスラッシュ（/）を含めてください。

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. メモ帳で、**[!UICONTROL File]**/**[!UICONTROL Save As]**&#x200B;をクリックして、編集したファイルを&#x200B;*Data Workbenchのインストールフォルダー*\User\*workingプロファイルー名*\Menu\Admin\Profile Managementに保存します。

   [!DNL .vw]ファイルの名前は、対応する[!DNL Profile Manager]内のディレクトリを反映するように変更してください。

1. （オプション）作業プロファイルのすべてのユーザーが変更を利用できるようにするには、[!DNL User]列の[!DNL .vw]ファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**&#x200B;をクリックします。
