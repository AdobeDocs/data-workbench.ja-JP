---
description: 特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。
title: ウィンドウデータのエクスポート
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 35%

---

# ウィンドウデータのエクスポート{#export-window-data}

特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。

グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

## ウィンドウデータをMicrosoft Excelにエクスポート{#section-b660adf7f4f64a2b9be7287c591b67b0}

個々のウィンドウデータを Microsoft Excel にエクスポートするには、以下の要件を満たしている必要があります。

* Microsoft ExcelがData Workbenchと同じマシンにインストールされている必要があります。
* Data Workbench処理を実行しているユーザーアカウントには、Microsoft Excelへのアクセス権が必要です。
* データを Excel ファイルとしてエクスポートする場合、Excel の新しいインスタンスが開かれます。
* Data Workbenchでは256列を超えるデータと65,536行のデータをサポートしていますが、バージョン8.0より前のMicrosoft Excelではサポートしていません。

これらの要件を満たしている場合、Data Workbenchは&#x200B;**[!UICONTROL Export To Excel]**&#x200B;メニューオプションを選択すると、Microsoft Excelに開始し、新しいExcelブックにデータをエクスポートします。

**ウィンドウデータを .xls または .xlsx ファイルにエクスポートするには**

ウィンドウの上の枠を右クリックし、**[!UICONTROL Export]**/**[!UICONTROL Export to Excel]**&#x200B;をクリックします。

![](assets/mnu_window_TitleBar_Export.png)

Excel で、エクスポートしたデータを含む新しいブックが開かれます。（次の節で説明するように）カスタムタイトルを指定していない限り、このブックには[!DNL Export title] （上の例のDay Table）を使用して名前が付けられます。

## カスタムタイトルの適用{#section-2a6559df812a470685e43923b7b9024e}

ウィンドウのカスタムタイトルを指定する場合（[!DNL Export]メニューの[!DNL Custom title]フィールドを使用）、Data Workbenchがデータをエクスポートするワークシートには、[!DNL Export title]フィールドのタイトルではなく、このカスタムタイトルを使用して名前が付けられます。

**ビジュアライゼーションにカスタムタイトルを適用するには**

1. ウィンドウの上の枠を右クリックし、**[!UICONTROL Custom title]**&#x200B;フィールドをクリックします。
1. you

![](assets/mnu_window_TitleBar_Export.png)

ビジュアライゼーションをExcelにエクスポートする場合、このウィンドウのデータを含むワークシートには、[!DNL Export title]フィールドのタイトルではなく、指定したタイトルを使用して名前が付けられます。

## ウィンドウデータをTSVファイルにエクスポート{#section-93c6b24f7338430aaf5a63b99b9489e8}

**ウィンドウを .tsv ファイルにエクスポートするには**

ウィンドウの上の枠を右クリックし、**[!UICONTROL Export]**/**[!UICONTROL Export TSV]**&#x200B;をクリックします。

1. [!DNL Save Window]ダイアログボックスが開きます。
1. ファイルを保存するディレクトリに移動します。必要に応じてファイル名を変更し、**[!UICONTROL Save]**&#x200B;をクリックします。
