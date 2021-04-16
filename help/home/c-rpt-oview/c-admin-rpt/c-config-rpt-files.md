---
description: レポートポータルでは、Report Serverで生成されたレポートをExcelファイル（.xlsまたは.xlsx）または.pngファイルとして表示できます。
title: Report.cfg ファイルの設定
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Report.cfg ファイルの設定{#configuring-report-cfg-files}

レポートポータルでは、Report Serverで生成されたレポートをExcelファイル（.xlsまたは.xlsx）または.pngファイルとして表示できます。

[!DNL Report Portal]にレポートセットを表示するには、[!DNL Report.cfg]ファイルでそのレポートセットの次のパラメーターを設定する必要があります。

* **[!UICONTROL Output Root]**&#x200B;パラメーターで、ポータルに使用するWebサーバーのドキュメントルートを指定します。
* **[!UICONTROL Report Types]**&#x200B;パラメーターで、生成するレポートタイプとしてExcel、png、サムネールを指定します。

[!DNL Report Server]は、指定した形式でレポートを生成すると、Webサーバーのドキュメントルートにこれらのファイルを配置します。このルートは、インストール時に[!DNL Report Portal]を設定してレポートにアクセスする場所です。

特定の[!DNL Report.cfg]パラメーターについて詳しくは、[Report.cfgパラメーター](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。
