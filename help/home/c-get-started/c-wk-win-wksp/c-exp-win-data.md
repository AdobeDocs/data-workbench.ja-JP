---
description: 特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。
title: ウィンドウデータのエクスポート
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 35%

---

# ウィンドウデータのエクスポート{#export-window-data}

{{eol}}

特定のウィンドウ内のデータを Excel ファイル（.xls または .xlsx）やタブ区切り値ファイル（.tsv）にエクスポートできます。

グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

## ウィンドウデータをMicrosoft Excel にエクスポート {#section-b660adf7f4f64a2b9be7287c591b67b0}

個々のウィンドウデータを Microsoft Excel にエクスポートするには、以下の要件を満たしている必要があります。

* Microsoft Excel は、Data Workbenchと同じマシンにインストールする必要があります。
* Data Workbench処理を実行するユーザーアカウントには、Microsoft Excel へのアクセス権が必要です。
* データを Excel ファイルとしてエクスポートする場合、Excel の新しいインスタンスが開かれます。
* Data Workbenchでは 256 列を超えるデータと 65,536 行のデータがサポートされていますが、8.0 より前のバージョンのMicrosoft Excel ではサポートされていません。

これらの要件を満たしている場合、Data Workbenchは、 **[!UICONTROL Export To Excel]** メニューオプション。

**ウィンドウデータを .xls または .xlsx ファイルにエクスポートするには**

ウィンドウの上の枠を右クリックし、 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**.

![](assets/mnu_window_TitleBar_Export.png)

Excel で、エクスポートしたデータを含む新しいブックが開かれます。（次の節で説明するように）カスタムタイトルを指定しない限り、このブックの名前は [!DNL Export title] （上記の例の日テーブル）。

## カスタムタイトルの適用 {#section-2a6559df812a470685e43923b7b9024e}

ウィンドウのカスタムタイトルを指定する場合 ( [!DNL Custom title] フィールド [!DNL Export] メニュー ) データのエクスポート先のData Workbenchに対して、ワークシート内のタイトルではなく、このカスタムタイトルを使用して名前が付けられます。 [!DNL Export title] フィールド（上記の例の日テーブル）

**ビジュアライゼーションにカスタムタイトルを適用するには**

1. ウィンドウの上の枠を右クリックし、 **[!UICONTROL Custom title]** フィールドに入力します。
1. you

![](assets/mnu_window_TitleBar_Export.png)

ビジュアライゼーションを Excel にエクスポートする際、このウィンドウのデータを含むワークシートには、 [!DNL Export title] フィールドに入力します。

## ウィンドウデータを TSV ファイルにエクスポート {#section-93c6b24f7338430aaf5a63b99b9489e8}

**ウィンドウを .tsv ファイルにエクスポートするには**

ウィンドウの上の枠を右クリックし、 **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**.

1. [!DNL Save Window]ダイアログボックスが開きます。
1. ファイルを保存するディレクトリに移動します。必要に応じてファイル名を変更し、 **[!UICONTROL Save]**.
