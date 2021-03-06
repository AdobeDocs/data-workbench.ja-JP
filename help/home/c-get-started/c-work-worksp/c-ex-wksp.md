---
description: ワークスペースを .png 画像ファイルとしてエクスポートしたり、特定のウィンドウのデータを Excel（.xls または .xlsx）ファイルにエクスポートできます。
title: ワークスペースのエクスポート
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 53%

---

# ワークスペースのエクスポート{#export-a-workspace}

ワークスペースを .png 画像ファイルとしてエクスポートしたり、特定のウィンドウのデータを Excel（.xls または .xlsx）ファイルにエクスポートできます。

## ワークスペースを PNG ファイルとしてエクスポート {#section-f9fbe0f0a1c341e2b063cce106cac35e}

ワークスペースのスナップショットを Portable Network Graphic 形式（`.png` ファイル）で保存できます。 ワークスペースを `.png` ファイルとして保存する場合は、次の色のオプションを使用できます。

* **暗い背景**&#x200B;は、ワークスペースを表示されているとおりにコピーします。
* **明るい背景**&#x200B;は、ワークスペースの要素をカラーでコピーし、白色背景で表示します。
* **モノクロ**&#x200B;は、ワークスペースの要素をグレースケールでコピーし、白色背景で表示します。

**ワークスペースを .png ファイルとしてエクスポートするには**

ワークスペースのタイトルバーメニューで、 **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>* をクリックします。

[!UICONTROL Save Image As]ダイアログボックスが開きます。

ファイルを保存するディレクトリに移動し、必要に応じてファイル名を変更して、**[!UICONTROL Save]** をクリックします。

## ワークスペースデータのMicrosoft Excel へのエクスポート {#section-fe214e3dbc364d2eba3834d62d295acb}

ワークスペースを Excel にエクスポートする場合、Data Workbench は、特定のビジュアライゼーションのデータ、ディメンションと値の凡例、テキスト注釈を、ワークシートごとに 1 つのビジュアライゼーションを持つ新しい Excel ブックにエクスポートします。

ワークスベースと個々のウィンドウを Microsoft Excel にエクスポートするには、以下の要件を満たしている必要があります。

* Microsoft Excel は、Data Workbenchと同じマシンにインストールする必要があります。
* Data Workbenchプロセスを実行しているユーザーアカウントには、Microsoft Excel へのアクセス権が必要です。

>[!NOTE]
>
>* データを Excel ファイルとしてエクスポートする場合、Excel の新しいインスタンスが開かれます。このプロセスの詳細については、[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757) を参照してください。
>* Data Workbenchでは 256 列を超え、65,536 行を超えるデータをサポートしていますが、8.0 より前のバージョンのMicrosoft Excel ではサポートされていません。
>


これらの要件を満たしている場合、Data Workbenchは自動的にMicrosoft Excel を起動し、データを新しい Excel ブックにエクスポートします。 グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブのビジュアライゼーションからはデータをエクスポートできません。

## カスタムタイトルの適用 {#section-a332e157554546cb8e88922a8d7a4fa2}

[!UICONTROL Export] メニューでウィンドウのカスタムタイトルを指定しない限り、一覧の [!UICONTROL Export title]（例：City Table）がワークシート名として使用されます。

1. ウィンドウの上の枠を右クリックし、「**[!UICONTROL Custom title]**」フィールドをクリックします。
1. ウィンドウに適用するタイトルを入力します。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>「[!UICONTROL Custom title]」フィールドにハイフン (-) を入力した場合、このビジュアライゼーションはワークスペースと共にエクスポートされません。

ワークスペースを Excel にエクスポートする場合、このウィンドウのデータを含むワークシートには、[!UICONTROL Export title] フィールドのタイトルではなく、指定したタイトルを使用して名前が付けられます。

## ワークスペースまたはサイドバーの Excel へのエクスポート {#section-360438b66d5f4734826ab463b4a01a75}

**ワークスペースデータを新しいまたはファイルにエクス [!DNL .xls] ポートす [!DNL .xlsx] るには**

1. ワークスペースのタイトルバーで、**[!UICONTROL Export]** > **[!UICONTROL Export]** をクリックします。
1. ワークスペースをエクスポートするか、サイドバーをエクスポートするか、両方をエクスポートするかを指定します。

## テンプレート Excel ファイルへのエクスポート {#section-814772929ca64cf6b92b89d3fdd02302}

ワークスペース内のデータをテンプレート Excel ファイル（`.xls` または `.xlsx`）にエクスポートできます。 テンプレートファイルを使用すると、ワークスペースをエクスポートするたびにデータのフォーマットに要する時間を短縮できます。

>[!NOTE]
>
>このテンプレートファイルは、`.xlt` ファイルではなく、`.xls` または `.xlsx` ファイルである必要があります。

データをエクスポートすると、テンプレート内の既存のタブ区切りシート（それぞれが 1 つのビジュアライゼーションを表す）にワークスペースの最新データが再設定されますが、タブ区切りシートとしてテンプレートに存在していない新しいウィンドウは無視されます。テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。

テーブルのビジュアライゼーションからエクスポートしたキャンペーンデータを円グラフや Excle ファイルの別のタブ区切りシートで使用して、この情報を週ごとに更新するものとします。テンプレートを使用すると、データを更新するたびにテーブルのタブ区切りシートから円グラフのタブ区切りシートへの参照を作成し直す必要がなくなります。テーブルデータはエクスポート時に更新され、それによって円グラフが自動的に更新されます。

**ワークスペースデータをテンプレートまたはファイルにエクス [!DNL .xls] ポートする [!DNL .xlsx] には**

1. ワークスペースのタイトルバーを右クリックし、 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]** をクリックします。
1. ワークスペースをエクスポートするか、サイドバーをエクスポートするか、両方をエクスポートするかを指定します。

   [!UICONTROL Select a template worksheet] ダイアログボックスが開きます。

1. 必要に応じて、以下の手順のどちらかを完了します。

   * `.xls` テンプレートファイルを使用している場合：

      1. テンプレート `.xls` を参照して選択します。
      1. 「**[!UICONTROL Open]**」をクリックします。
   * `.xlsx` テンプレートファイルを使用している場合：

      1. テンプレートファイルの場所を参照します。`.xlsx` ファイル名は表示されません。
      1. 「[!UICONTROL File name]」フィールドに「`.xlsx`」と入力し、「**[!UICONTROL Open]**」をクリックします。 すべての `.xlsx` ファイル名がファイルリストに表示されます。

      1. テンプレート `.xlsx` ファイルを選択します。
      1. 「**[!UICONTROL Open]**」をクリックします。
