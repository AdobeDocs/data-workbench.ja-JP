---
description: Excel ファイルとしてレポートを生成するための情報です。
title: Microsoft Excel ファイルとしてのレポートの生成
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 20%

---

# Microsoft Excel ファイルとしてのレポートの生成{#generating-reports-as-microsoft-excel-files}

Excel ファイルとしてレポートを生成するための情報です。

以下の要件を満たす必要があります。

* Microsoft Excel が [!DNL Report Server] と同じコンピューターにインストールされていること。
* [!DNL Report Server] の処理を実行中のユーザーアカウントが Microsoft Excel にアクセスする権限を持っていること。

   >[!NOTE]
   >
   >
   >
   >
   >    * Excel ファイルとしてレポートを生成する場合、Excel の新しいインスタンスが開きます。 このプロセスの詳細については、[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757) を参照してください。
   >    * Data Workbench では 256 列を超え、65,536 行を超えるデータをサポートしていますが、Microsoft Excel ではサポートしていません。


これらの要件を満たすと、 [!DNL Report Server] は自動的にMicrosoft Excel を起動し、特定のビジュアライゼーション、ディメンションと値の凡例、テキスト注釈のデータを、ワークシートごとに 1 つのビジュアライゼーションを持つ新しい Excel ワークブックに出力します。

>[!NOTE]
>
>グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

ビジュアライゼーションに [!DNL Custom Title] を指定していない限り、ウィンドウのタイプ（例：Movie Table）がワークシート名として使用されます。

ビジュアライゼーションに [!DNL Custom Titles] を指定する方法について詳しくは、『[Data Workbenchクライアントガイド ](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=ja)』を参照してください。

## テンプレートファイルの使用 {#section-40ab11916f464b1a88214ab969da6751}

また、テンプレートの Excel（[!DNL .xls] または [!DNL .xlsx]）ファイルを使用して、Excel ファイルとしてレポートを生成することもできます。 テンプレートファイルを使用すると、レポートが生成されるたびにデータのフォーマットに費やす時間を短縮できます。

このテンプレートファイルは、[!DNL .xlt] ファイルではなく、[!DNL .xls] または [!DNL .xlsx] ファイルである必要があります。

個々のレポートのテンプレート、すべてのレポートの汎用テンプレート、またはその両方を定義できます。 これら 2 つの項目は相互に排他的ではないので、汎用テンプレートを定義し、特定のテンプレートも定義できます。

すべてのレポートで使用する汎用テンプレートを使用してレポートを生成するには、[!DNL Report.cfg] の Excel Template パラメータでその Excel ファイルの名前を指定し、そのレポートセットの [!DNL Report.cfg] と同じフォルダ (*data workbench installation directory*\*ProfileName*\Reports\*ReportSetSetSetname*) と入力します。 このパラメーターについて詳しくは、[Report.cfg のパラメーター ](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff) を参照してください。

レポートに固有のテンプレートを使用してレポートを生成するには、Excel ファイルにレポートワークスペース ([!DNL .vw]) ファイルと同じ名前を付け、そのテンプレートファイルをレポートワークスペース ([!DNL .vw]) ファイルと同じフォルダに配置する必要があります。

レポートの生成時に、テンプレート内の既存のタブ付きシート（各シートは 1 つのビジュアライゼーションを表します）には、レポートの最新のデータが再入力されますが、テンプレートにタブ付きシートとして存在しない新しいウィンドウは無視されます。 テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。
