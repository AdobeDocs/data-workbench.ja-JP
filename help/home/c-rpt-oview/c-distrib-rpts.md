---
description: レポートが生成されると、ReportはそのReport.cfgファイル内の設定に基づいて、セット内のレポートを配信します。
title: レポートの配信
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# レポートの配信{#distributing-reports}

レポートが生成されると、ReportはそのReport.cfgファイル内の設定に基づいて、セット内のレポートを配信します。

[!DNL Report] では、次の方法を使用して、セット内のレポートを配布できます。

* **電子メール：** レポートをExcelファイル、ファイル、またはサムネールとして電子メール（インラインまたは添付ファイル）で配布するに [!DNL .png] は、レポートセットのファイルで「メールレポート」パラメーターを指定 [!DNL Report.cfg] します。セット内のすべてのレポートは、指定した受信者に1件のメッセージで電子メールで送信されます。

* **共有ディレクトリ：** レポートをExcelファイル、ファイルまたはサムネールとして共有ディレクトリに配布するに [!DNL .png] は、レポートセットのファイルの出力ルートパラメーターにディレクトリを指定 [!DNL Report.cfg] します。

* **Reporting Portal:** レポートポータルを使用すると、Webブラウザーでレポートを表示できます。Adobeの[!DNL Report Portal]には、Excelまたは[!DNL .png]ファイルとして生成されたレポートが表示されますが、サムネール([!DNL .jpg])として生成されたレポートは表示されません。 レポートをポータルに配布するには、そのポータルで使用するWebサーバーのドキュメントルートを、レポートセットの[!DNL Report.cfg]ファイルの「出力ルート」パラメーターに指定します。 [!DNL Report Portal]のインストールと使用について詳しくは、「[Report Portalの操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)」を参照してください。

>[!NOTE]
>
>[!DNL Report]で現在サポートされている出力を読み取るには、目的の形式でレポートを表示できるアプリケーションが必要です。 例えば、[!DNL .xlsx]ファイルを表示するには、Microsoft Excel 2007以降が必要です。

また、これらの生成オプションと配布オプションの組み合わせを使用することもできます。 例えば、[!DNL Report Types]パラメーターを設定してレポートセットをExcelおよび[!DNL .png]ファイルとして生成し、[!DNL Mail Report]および[!DNL Output Root]パラメーターを設定した場合、指定した出力ディレクトリ（ポータルで表示する場合もあります）に配信され、1通の電子メールで受信者に送信されます。

レポートセットを設定する手順については、[レポートセットの操作](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)を参照してください。 特定の[!DNL Report.cfg]パラメーターについて詳しくは、[Report.cfgのパラメーター](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。
