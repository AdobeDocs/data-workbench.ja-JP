---
description: Excelファイルとしてレポートを生成するための情報です。
title: Microsoft Excel ファイルとしてのレポートの生成
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 23%

---

# Microsoft Excel ファイルとしてのレポートの生成{#generating-reports-as-microsoft-excel-files}

Excelファイルとしてレポートを生成するための情報です。

以下の要件を満たす必要があります。

* Microsoft Excel が [!DNL Report Server] と同じコンピューターにインストールされていること。
* [!DNL Report Server] の処理を実行中のユーザーアカウントが Microsoft Excel にアクセスする権限を持っていること。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Excelファイルとしてのレポートを生成する場合、Excelの新しいインスタンスが開かれます。 この処理について詳しくは、[http://support.microsoft.com/ja-jp/kb/257757](http://support.microsoft.com/kb/257757) を参照してください。
   >    * data workbenchでは256列を超えるデータと65,536行のデータをサポートしていますが、Microsoft Excelではサポートしていません。


これらの要件を満たしている場合、[!DNL Report Server]はMicrosoft Excelを自動的に開始し、特定のビジュアライゼーション、ディメンションおよび値の凡例のデータとテキスト注釈を、ワークシートごとに1つのビジュアライゼーションを持つ新しいExcelワークブックに出力します。

>[!NOTE]
>
>グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

ビジュアライゼーションに[!DNL Custom Title]を指定していない限り、ウィンドウのタイプ（ムービーテーブルなど）がワークシート名として使用されます。

ビジュアライゼーションに対して[!DNL Custom Titles]を指定する方法について詳しくは、『[Data Workbenchクライアントガイド](https://docs.adobe.com/content/help/ja-JP/data-workbench/using/client/t-open-ins.html)』を参照してください。

## テンプレートファイルの使用{#section-40ab11916f464b1a88214ab969da6751}

また、テンプレートExcel （ [!DNL .xls]または[!DNL .xlsx]）ファイルを使用して、Excelファイルとしてレポートを生成することもできます。 テンプレートファイルを使用すると、レポートを生成するたびにデータの書式設定に費やす時間を短縮できます。

このテンプレートファイルは[!DNL .xlt]ファイルではなく、[!DNL .xls]ファイルまたは[!DNL .xlsx]ファイルでなければなりません。

個々のレポートごとにテンプレートを定義するか、全レポート用の汎用テンプレートを定義するか、両方を組み合わせて定義するかを選択できます。 この2つの項目は相互に排他的でないので、汎用テンプレートを定義してから、特定のテンプレートも定義できます。

全レポートで使用する汎用テンプレートを使用してレポートを生成するには、そのレポートセットファイルの[!DNL Report.cfg]のデフォルトのExcelテンプレートパラメーターにそのExcelファイルの名前を指定し、そのレポートセットの[!DNL Report.cfg]と同じフォルダーに配置します。name*)。 **&#x200B;このパラメーターについて詳しくは、[Report.cfgパラメーター](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。

レポートに固有のテンプレートを使用してレポートを生成するには、Excelファイルにレポートワークスペース( [!DNL .vw])ファイルと同じ名前を付け、そのテンプレートファイルをレポートワークスペース( [!DNL .vw])ファイルと同じフォルダーに配置します。

レポートが生成されると、テンプレート内の既存のタブ付きシート（各シートは1つのビジュアライゼーションを表します）に、レポートの最新のデータが再入力されます。一方、テンプレート内にタブ付きシートとして存在しない新しいウィンドウは無視されます。 テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。
