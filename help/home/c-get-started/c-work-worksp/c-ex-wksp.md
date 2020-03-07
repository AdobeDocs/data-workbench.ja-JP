---
description: ワークスペースを .png 画像ファイルとしてエクスポートしたり、特定のウィンドウのデータを Excel（.xls または .xlsx）ファイルにエクスポートできます。
solution: Analytics
title: ワークスペースの書き出し
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ワークスペースの書き出し{#export-a-workspace}

ワークスペースを .png 画像ファイルとしてエクスポートしたり、特定のウィンドウのデータを Excel（.xls または .xlsx）ファイルにエクスポートできます。

## ワークスペースをPNGファイルとして書き出す {#section-f9fbe0f0a1c341e2b063cce106cac35e}

You can save a snapshot of a workspace in Portable Network Graphic format (`.png` files). The following color options are available when saving workspaces as `.png` files:

* **暗い背景**&#x200B;は、ワークスペースを表示されているとおりにコピーします。
* **明るい背景**&#x200B;は、ワークスペースの要素をカラーでコピーし、白色背景で表示します。
* **モノクロ**&#x200B;は、ワークスペースの要素をグレースケールでコピーし、白色背景で表示します。

**ワークスペースを .png ファイルとしてエクスポートするには**

ワークスペースのタイトルバーメニューで、// **[!UICONTROL Export]** &lt;> **[!UICONTROL Export PNG]** をクリ *ック&#x200B;**[!UICONTROL color option]**します*。

ダイアログ [!UICONTROL Save Image As] ボックスが表示されます。

Navigate to the directory in which you want to save the file, change the name of the file if necessary, and click **[!UICONTROL Save]**.

## Export workspace data to Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

ワークスペースを Excel にエクスポートする場合、Data Workbench は、特定のビジュアライゼーションのデータ、ディメンションと値の凡例、テキスト注釈を、ワークシートごとに 1 つのビジュアライゼーションを持つ新しい Excel ブックにエクスポートします。

ワークスベースと個々のウィンドウを Microsoft Excel にエクスポートするには、以下の要件を満たしている必要があります。

* Data Workbenchと同じマシンにMicrosoft Excelをインストールする必要があります。
* Data Workbenchプロセスが実行されているユーザーアカウントには、Microsoft Excelへのアクセス権が必要です。

>[!NOTE]
>
>* データを Excel ファイルとしてエクスポートする場合、Excel の新しいインスタンスが開かれます。この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。
>* Data Workbenchでは256列を超えるデータ行と65,536行のデータをサポートしていますが、8.0より前のバージョンのMicrosoft Excelではサポートしていません。
>



これらの要件を満たしている場合、Data WorkbenchはMicrosoft Excelを自動的に起動し、データを新しいExcelワークブックにエクスポートします。 グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブのビジュアライゼーションからはデータをエクスポートできません。

## カスタムタイトルの適用 {#section-a332e157554546cb8e88922a8d7a4fa2}

Unless you have specified a Custom title for the window on the [!UICONTROL Export] menu, the [!UICONTROL Export title] listed (for example, City Table) is used as the worksheet name.

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field.
1. ウィンドウに適用するタイトルを入力します。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>If you enter a hyphen (-) in the [!UICONTROL Custom title] field, this visualization is not exported with the workspace.

When you export the workspace to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!UICONTROL Export title] field.

## Export a workspace or sidebar to Excel {#section-360438b66d5f4734826ab463b4a01a75}

**ワークスペースデータを新しいまたはファイルにエクスポ[!DNL .xls]ートする[!DNL .xlsx]には**

1. In title bar of the workspace, click **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. ワークスペースをエクスポートするか、サイドバーをエクスポートするか、両方をエクスポートするかを指定します。

## Export to a template Excel file {#section-814772929ca64cf6b92b89d3fdd02302}

You can export data in your workspace to a template Excel file (`.xls` or `.xlsx`). テンプレートファイルを使用すると、ワークスペースをエクスポートするたびにデータのフォーマットに要する時間を短縮できます。

>[!NOTE]
>
>This template file must be an `.xls` or `.xlsx` file, not an `.xlt` file.

データをエクスポートすると、テンプレート内の既存のタブ区切りシート（それぞれが 1 つのビジュアライゼーションを表す）にワークスペースの最新データが再設定されますが、タブ区切りシートとしてテンプレートに存在していない新しいウィンドウは無視されます。テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。

テーブルのビジュアライゼーションからエクスポートしたキャンペーンデータを円グラフや Excle ファイルの別のタブ区切りシートで使用して、この情報を週ごとに更新するものとします。テンプレートを使用すると、データを更新するたびにテーブルのタブ区切りシートから円グラフのタブ区切りシートへの参照を作成し直す必要がなくなります。テーブルデータはエクスポート時に更新され、それによって円グラフが自動的に更新されます。

**ワークスペースデータをテンプレートまたはファイルにエク[!DNL .xls]スポートする[!DNL .xlsx]には**

1. ワークスペースのタイトルバーを右クリックし、/をクリッ **[!UICONTROL Export]** クしま **[!UICONTROL Export to Excel from Template]**&#x200B;す。
1. ワークスペースをエクスポートするか、サイドバーをエクスポートするか、両方をエクスポートするかを指定します。

   ダイアログ [!UICONTROL Select a template worksheet] ボックスが開きます。

1. 必要に応じて、以下の手順のどちらかを完了します。

   * If you are using a `.xls` template file:

      1. Browse to and select the template `.xls` file.
      1. クリック **[!UICONTROL Open]**.
   * If you are using a `.xlsx` template file:

      1. テンプレートファイルの場所を参照します。The `.xlsx` file name is not displayed.
      1. フィールドに [!UICONTROL File name] と入力し、をク `.xlsx` リックしま **[!UICONTROL Open]**&#x200B;す。 All `.xlsx` file names display in the file list.

      1. Select the template `.xlsx` file.
      1. クリック **[!UICONTROL Open]**.


