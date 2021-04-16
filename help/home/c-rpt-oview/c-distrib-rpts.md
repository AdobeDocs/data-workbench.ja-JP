---
description: レポートが生成されると、Report.cfgファイル内の設定に基づいて、レポートがセット内のレポートを配信します。
title: レポートの配信
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# レポートの配信{#distributing-reports}

レポートが生成されると、Report.cfgファイル内の設定に基づいて、レポートがセット内のレポートを配信します。

[!DNL Report] 次の方法を使用して、セット内のレポートを配信できます。

* **電子メール：Excelファイル、** ファイルまたはサムネールとしてレポートを電子メール（インラインまたは添付ファイル）で配信するには、レポートセットの [!DNL .png]  [!DNL Report.cfg] ファイルで「メールレポート」パラメーターを指定します。そのセット内のすべてのレポートは、指定した受信者に1通のメッセージで電子メールで送信されます。

* **共有ディレクトリ：レポート** をExcelファイル、 [!DNL .png] ファイルまたはサムネールとして共有ディレクトリに配信するには、レポートセットのフ [!DNL Report.cfg] ァイルのOutput Rootパラメーターにディレクトリを指定します。

* **レポートポータル：レポートポータル** を使用すると、Webブラウザーを介してレポートを表示できます。Adobeの[!DNL Report Portal]は、Excelまたは[!DNL .png]ファイルとして生成されたレポートを表示しますが、サムネールとして生成されたレポート([!DNL .jpg])は表示しません。 レポートをポータルに配信するには、そのポータルで使用するWebサーバーのドキュメントルートを、レポートセットの[!DNL Report.cfg]ファイルのOutput Rootパラメーターに指定します。 [!DNL Report Portal]のインストールと使用について詳しくは、[レポートポータルの操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)を参照してください。

>[!NOTE]
>
>[!DNL Report]が現在サポートしている出力を読み取るには、レポートを目的の形式で表示できるアプリケーションが必要です。 例えば、[!DNL .xlsx]ファイルを表示するには、Microsoft Excel 2007以降が必要です。

また、これらの生成オプションと配信オプションを組み合わせて使用することもできます。 例えば、[!DNL Report Types]パラメーターを設定してレポートセットをExcelおよび[!DNL .png]ファイルとして生成し、[!DNL Mail Report]および[!DNL Output Root]パラメーターを設定した場合、そのセット内のすべてのレポートは指定した出力ディレクトリに配布され（おそらくポータルで表示されます）、1通の電子メールで受信者に送信されます。

レポートセットを設定する手順については、[レポートセットの操作](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)を参照してください。 特定の[!DNL Report.cfg]パラメーターについて詳しくは、[Report.cfgパラメーター](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。
