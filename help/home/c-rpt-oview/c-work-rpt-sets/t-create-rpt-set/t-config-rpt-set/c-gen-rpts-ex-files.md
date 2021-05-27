---
description: レポートをExcelファイルとして生成するための情報です。
title: Microsoft Excel ファイルとしてのレポートの生成
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 23%

---

# Microsoft Excel ファイルとしてのレポートの生成{#generating-reports-as-microsoft-excel-files}

レポートをExcelファイルとして生成するための情報です。

以下の要件を満たす必要があります。

* Microsoft Excel が [!DNL Report Server] と同じコンピューターにインストールされていること。
* [!DNL Report Server] の処理を実行中のユーザーアカウントが Microsoft Excel にアクセスする権限を持っていること。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * レポートをExcelファイルとして生成する場合、Excelの新しいインスタンスを開くことになります。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。
   >    * Data Workbenchでは256列を超え、65,536行を超えるデータをサポートしていますが、Microsoft Excelではサポートしていません。


これらの要件を満たすと、 [!DNL Report Server]は自動的にMicrosoft Excelを起動し、特定のビジュアライゼーション、ディメンションと値の凡例、テキスト注釈のデータを、1つのワークシートにつき1つのビジュアライゼーションを持つ新しいExcelワークブックに出力します。

>[!NOTE]
>
>グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

ビジュアライゼーションに[!DNL Custom Title]を指定していない限り、ウィンドウのタイプ（例：Movie Table）がワークシート名として使用されます。

ビジュアライゼーションに[!DNL Custom Titles]を指定する方法について詳しくは、『[Data Workbenchクライアントガイド](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/client/t-open-ins.html)』を参照してください。

## テンプレートファイル{#section-40ab11916f464b1a88214ab969da6751}の使用

また、テンプレートのExcel（[!DNL .xls]または[!DNL .xlsx]）ファイルを使用して、Excelファイルとしてレポートを生成することもできます。 テンプレートファイルを使用すると、レポートが生成されるたびにデータのフォーマットに費やす時間を短縮できます。

このテンプレートファイルは、[!DNL .xlt]ファイルではなく、[!DNL .xls]または[!DNL .xlsx]ファイルである必要があります。

個々のレポートごとにテンプレートを定義するか、すべてのレポート用の汎用テンプレートを定義するか、またはその両方を定義するかを選択できます。 これら2つの項目は相互に排他的ではないので、汎用テンプレートを定義してから、特定のテンプレートも定義できます。

すべてのレポートで使用する汎用テンプレートを使用してレポートを生成するには、[!DNL Report.cfg]のExcel TemplateパラメーターにそのExcelファイルの名前を指定し、そのレポートセットの[!DNL Report.cfg]と同じフォルダー(*data workbench installation directory*\*\Reports\*ReportSetSetName*name*)と入力します。 このパラメーターについて詳しくは、[Report.cfgのパラメーター](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。

レポートに固有のテンプレートを使用してレポートを生成するには、Excelファイルにレポートワークスペース([!DNL .vw])ファイルと同じ名前を付けてから、レポートワークスペース([!DNL .vw])ファイルと同じフォルダーに配置します。

レポートが生成されると、テンプレート内の既存のタブ付きシート（各ページは1つのビジュアライゼーションを表します）には、レポートの最新のデータが再入力されますが、テンプレートにタブ付きシートとして存在しない新しいウィンドウは無視されます。 テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。
