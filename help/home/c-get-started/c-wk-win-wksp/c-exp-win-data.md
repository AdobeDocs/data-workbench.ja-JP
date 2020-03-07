---
description: 特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。
solution: Analytics
title: ウィンドウデータの書き出し
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ウィンドウデータの書き出し{#export-window-data}

特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。

グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

## Export window data to Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

個々のウィンドウデータを Microsoft Excel にエクスポートするには、以下の要件を満たしている必要があります。

* Data Workbenchと同じマシンにMicrosoft Excelをインストールする必要があります。
* Data Workbenchプロセスが実行されているユーザーアカウントには、Microsoft Excelへのアクセス権が必要です。
* データを Excel ファイルとしてエクスポートする場合、Excel の新しいインスタンスが開かれます。
* Data Workbenchでは256列を超えるデータ行と65,536行のデータをサポートしていますが、8.0より前のバージョンのMicrosoft Excelではサポートしていません。

If these requirements are met, Data Workbench automatically starts Microsoft Excel and export the data to a new Excel workbook when you select the **[!UICONTROL Export To Excel]** menu option.

**ウィンドウデータを .xls または .xlsx ファイルにエクスポートするには**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel で、エクスポートしたデータを含む新しいブックが開かれます。Unless you have provided a Custom title (as described in the following section), this workbook is named using the [!DNL Export title] (Day Table in the example above).

## カスタムタイトルの適用 {#section-2a6559df812a470685e43923b7b9024e}

If you provide a custom title for a window (using the [!DNL Custom title] field on the [!DNL Export] menu) the worksheet to which Data Workbench exports the data is named using this custom title instead of the title in the [!DNL Export title] field (Day Table in the example above).

**ビジュアライゼーションにカスタムタイトルを適用するには**

1. Right-click the top border of the window and click in the **[!UICONTROL Custom title]** field.
1. you

![](assets/mnu_window_TitleBar_Export.png)

When you export the visualization to Excel, the worksheet containing the data for this window is named using the title that you specified instead of the title in the [!DNL Export title] field.

## Export window data to a TSV file {#section-93c6b24f7338430aaf5a63b99b9489e8}

**ウィンドウを .tsv ファイルにエクスポートするには**

Right-click the top border of the window and click **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. ダイアログ [!DNL Save Window] ボックスが表示されます。
1. Navigate to the directory in which you want to save the file. Change the name of the file if necessary, and click **[!UICONTROL Save]**.

