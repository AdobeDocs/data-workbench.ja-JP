---
description: レポートポータルでは、Report Serverで生成されたレポートをExcelファイル（.xlsまたは.xlsx）または.pngファイルとして表示できます。
solution: Analytics
title: Report.cfgファイルの設定
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Report.cfgファイルの設定{#configuring-report-cfg-files}

レポートポータルでは、Report Serverで生成されたレポートをExcelファイル（.xlsまたは.xlsx）または.pngファイルとして表示できます。

にレポートセットを表示するに [!DNL Report Portal]は、そのレポートセットのファイルに次のパラメ [!DNL Report.cfg] ータを設定する必要があります。

* このパラメ **[!UICONTROL Output Root]** ーターで、ポータルに使用するWebサーバーのドキュメントルートを指定します。
* パラメータ **[!UICONTROL Report Types]** ーで、生成するレポートタイプとしてExcel、pngまたはサムネールを指定します。

が指定 [!DNL Report Server] した形式でレポートを生成すると、Webサーバーのドキュメントルートにこれらのファイルが配置されます。このルートは、をインストールする際に、レポートにアクセスするよ [!DNL Report Portal] うに設定する場所です。

特定のパラメーターについて詳し [!DNL Report.cfg] くは、 [Report.cfgのパラメーターを参照してください](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
