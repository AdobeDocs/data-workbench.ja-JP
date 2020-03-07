---
description: レポートの生成後、Report.cfgファイル内の設定に基づいて、レポートセット内のレポートが配信されます。
solution: Analytics
title: レポートの配信
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートの配信{#distributing-reports}

レポートの生成後、Report.cfgファイル内の設定に基づいて、レポートセット内のレポートが配信されます。

[!DNL Report] を使用すると、次の方法を使用して、レポートをセット内で配信できます。

* **電子メール：** レポートをExcelファイル、ファイル、または電子メー [!DNL .png] ル（インラインまたは添付ファイル）経由で配信するには、レポートセットのファイルで「メールレポート」パラメーターを指定 [!DNL Report.cfg] します。 そのセット内のすべてのレポートは、指定した受信者に1通のメッセージで電子メールで送信されます。

* **共有ディレクトリ：** レポートをExcelファイル、ファイルまたはサムネールと [!DNL .png] して共有ディレクトリに配信するには、レポートセットのファイルのOutput Rootパラメーターでディレクトリを指定 [!DNL Report.cfg] します。

* **レポートポータル：** レポートポータルでは、Webブラウザーを使用してレポートを表示できます。 アドビでは、Excelま [!DNL Report Portal] たはファイルとして生成されたレ [!DNL .png] ポートを表示しますが、サムネール( [!DNL .jpg])としては表示しません。 レポートをポータルに配信するには、レポートセットのファイルのOutput Rootパラメーターで、ポータルに使用するWebサーバーのドキュメントルートを指定し [!DNL Report.cfg] ます。 のインストールと使用について詳しくは、「レポー [!DNL Report Portal]トポータル [の使用」を参照してくださ](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)い。

>[!NOTE]
>
>で現在サポートされている出力を読み取るに [!DNL Report]は、レポートを目的の形式で表示できるアプリケーションが必要です。 たとえば、ファイルを表 [!DNL .xlsx] 示するには、Microsoft Excel 2007以降が必要です。

また、これらの生成オプションと配布オプションを組み合わせて使用することもできます。 例えば、レポートセットをExcelおよびファイルとして生成するようにパラメーターを設定し、およびパラメーターを設定した場合、そのセット内のすべてのレポートは指定した出力ディレクトリ（おそらくポータルで表示）に配信され、1つの電子メールで受信者に送信されます。 [!DNL Report Types][!DNL .png][!DNL Mail Report][!DNL Output Root]

レポートセットを設定する手順については、「レポートセッ [トの操作」を参照してください](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 特定のパラメーターについて詳し [!DNL Report.cfg] くは、 [Report.cfgのパラメーターを参照してください](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
