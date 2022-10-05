---
description: レポートを Excel ファイルとして生成するための情報です。
title: Microsoft Excel ファイルとしてのレポートの生成
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 20%

---

# Microsoft Excel ファイルとしてのレポートの生成{#generating-reports-as-microsoft-excel-files}

{{eol}}

レポートを Excel ファイルとして生成するための情報です。

以下の要件を満たす必要があります。

* Microsoft Excel が [!DNL Report Server] と同じコンピューターにインストールされていること。
* [!DNL Report Server] の処理を実行中のユーザーアカウントが Microsoft Excel にアクセスする権限を持っていること。

   >[!NOTE]
   >
   >
   >
   >
   >    * レポートを Excel ファイルとして生成する場合、Excel の新しいインスタンスを開こうとしています。 このプロセスについて詳しくは、 [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
   >    * Data Workbench では 256 列を超えるデータと 65,536 行のデータがサポートされていますが、Microsoft Excel ではサポートされていません。


これらの要件が満たされている場合、 [!DNL Report Server] は自動的にMicrosoft Excel を起動し、特定のビジュアライゼーション、ディメンションと値の凡例、テキスト注釈のデータを、ワークシートごとに 1 つのビジュアライゼーションを持つ新しい Excel ワークブックに出力します。

>[!NOTE]
>
>グラフ、パスブラウザー、プロセスマップ、散布グラフ、グローブからはデータをエクスポートできません。

指定した [!DNL Custom Title] ビジュアライゼーションの場合、ウィンドウのタイプ（例：Movie Table）がワークシート名として使用されます。

詳しくは、 [!DNL Custom Titles] ビジュアライゼーションについては、 [Data Workbenchクライアントガイド](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html?lang=ja).

## テンプレートファイルの使用 {#section-40ab11916f464b1a88214ab969da6751}

また、テンプレート Excel ( [!DNL .xls] または [!DNL .xlsx]) ファイルです。 テンプレートファイルを使用すると、レポートが生成されるたびにデータの書式設定に費やす時間を短縮できます。

このテンプレートファイルは、 [!DNL .xls] または [!DNL .xlsx] ファイル（ではない） [!DNL .xlt] ファイル。

個々のレポートのテンプレート、すべてのレポートの汎用テンプレート、またはその両方を定義できます。 これら 2 つの項目は相互に排他的ではないので、汎用テンプレートを定義してから、特定のテンプレートも定義できます。

すべてのレポートで使用する汎用テンプレートを使用してレポートを生成するには、Excel ファイルの名前を [!DNL Report.cfg] このレポートセットファイルの [!DNL Report.cfg] ()*data workbench のインストールディレクトリ*\*ProfileName*\Reports\*ReportSetName*)。 このパラメーターについて詳しくは、 [Report.cfg のパラメーター](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

レポートに固有のテンプレートを使用してレポートを生成するには、Excel ファイルにレポートワークスペース ( [!DNL .vw]) ファイルを作成してから、レポートワークスペースと同じフォルダー ( [!DNL .vw]) ファイルです。

レポートが生成されると、テンプレート内の既存のタブ付きシート（各シートは 1 つのビジュアライゼーションを表します）には、レポートの最新のデータが再入力されますが、テンプレート内にタブ付きシートとして存在しない新しいウィンドウは無視されます。 テンプレートファイル内のその他すべてのタブ区切りシートは、変更されないままです。

また、レポートの生成時に自動的に実行したいマクロをテンプレート Excel ファイルに定義した場合は、マクロの名前を「VSExport」にしてください。
