---
description: レポートをExcelファイルとして生成するための情報です。
solution: Analytics
title: Microsoft Excelファイルとしてのレポートの生成
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Microsoft Excelファイルとしてのレポートの生成{#generating-reports-as-microsoft-excel-files}

レポートをExcelファイルとして生成するための情報です。

次の要件を満たす必要があります。

* Microsoft Excel が [!DNL Report Server] と同じコンピューターにインストールされていること。
* [!DNL Report Server] の処理を実行中のユーザーアカウントが Microsoft Excel にアクセスする権限を持っていること。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Excelファイルとしてレポートを生成する場合、Excelの新しいインスタンスを開きます。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。
   >    * Data Workbenchでは、256列を超えるデータと65,536行のデータをサポートしていますが、Microsoft Excelではサポートしていません。


これらの要件を満たす場合、は [!DNL Report Server] Microsoft Excelを自動的に起動し、特定のビジュアライゼーション、ディメンションと値の凡例、およびテキスト注釈のデータを、ワークシートごとに1つのビジュアライゼーションを持つ新しいExcelワークブックに出力します。

>[!NOTE]
>
>グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

ビジュアライゼーションのタ [!DNL Custom Title] イプを指定していない限り、ウィンドウのタイプ（ムービーテーブルなど）がワークシート名として使用されます。

ビジュアライゼーションの指定につ [!DNL Custom Titles] いて詳しくは、『 [Data Workbenchクライアントガイド』を参照してください](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)。

## テンプレートファイルの使用 {#section-40ab11916f464b1a88214ab969da6751}

また、テンプレートのExcel（または）ファイルを使用して、Excelファイルとしてレポートを生 [!DNL .xls] 成するこ [!DNL .xlsx]ともできます。 テンプレートファイルを使用すると、レポートが生成されるたびにデータの形式設定に費やす時間を短縮できます。

This template file must be an [!DNL .xls] or [!DNL .xlsx] file, not an [!DNL .xlt] file.

個々のレポートのテンプレート、すべてのレポートの汎用テンプレート、またはその両方を組み合わせて定義できます。 この2つの項目は相互に排他的ではないので、汎用テンプレートを定義し、特定のテンプレートも定義できます。

すべてのレポートで使用する汎用テンプレートを使用してレポートを生成するには、そのレポートセットファイルのデフォルトのExcelテンプレートパラメーターにそのExcelファイルの名前を指定し、そのレポートセットのと同じフォルダー( [!DNL Report.cfg] data workbench installation directory [!DNL Report.cfg]**\*ProfileName*\Reports\*ReportSetName*)にテンプレートファイルを配置します。 このパラメーターについて詳しくは、 [Report.cfgのパラメーターを参照してください](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

レポートに固有のテンプレートを使用してレポートを生成するには、Excelファイルにレポートワークスペース( [!DNL .vw])ファイルと同じ名前を付け、そのテンプレートファイルをレポートワークスペース( [!DNL .vw])ファイルと同じフォルダに配置します。

レポートを生成すると、テンプレート内の既存のタブ付きシート（各シートは1つのビジュアライゼーションを表します）に、レポートの最新のデータが再入力されますが、テンプレート内にタブ付きシートとして存在しない新しいウィンドウは無視されます。 テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。
