---
description: レポートが生成されると、Report.cfg ファイル内の設定に基づいて、セット内のレポートが配信されます。
title: レポートの配信
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# レポートの配信{#distributing-reports}

{{eol}}

レポートが生成されると、Report.cfg ファイル内の設定に基づいて、セット内のレポートが配信されます。

[!DNL Report] では、次の方法を使用して、レポートをセット内で配布できます。

* **電子メール：** レポートを Excel ファイルとして配布するには [!DNL .png] ファイルまたは電子メール経由のサムネール（インラインまたは添付ファイル）で、レポートセットの [!DNL Report.cfg] ファイル。 セット内のすべてのレポートは、指定した受信者宛てに 1 つのメッセージで電子メールで送信されます。

* **共有ディレクトリ：** レポートを Excel ファイルとして配布するには [!DNL .png] ファイルまたは共有ディレクトリへのサムネールの場合は、レポートセットの [!DNL Report.cfg] ファイル。

* **レポートポータル：** レポートポータルでは、Web ブラウザーを使用してレポートを表示できます。 Adobe [!DNL Report Portal] Excel または [!DNL .png] ファイルをサムネールとして生成するものではなく、サムネール ( [!DNL .jpg]) をクリックします。 レポートをポータルに配布するには、ポータルに使用する Web サーバーのドキュメントルートを、レポートセットの [!DNL Report.cfg] ファイル。 のインストールと使用に関する詳細 [!DNL Report Portal]を参照してください。 [Report Portal の操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>現在、がサポートしている出力を読み取るには [!DNL Report]を使用する場合は、目的の形式でレポートを表示できるアプリケーションが必要です。 例えば、次を表示するには： [!DNL .xlsx] ファイルには、Microsoft Excel 2007 以降が必要です。

また、これらの生成オプションと配布オプションの組み合わせを使用することもできます。 例えば、 [!DNL Report Types] Excel としてレポートセットを生成するためのパラメーターおよび [!DNL .png] ファイルを選択し、 [!DNL Mail Report]および [!DNL Output Root] パラメーターを指定すると、そのセット内のすべてのレポートが指定した出力ディレクトリ（ポータル内で表示される場合もあります）に配信され、受信者宛に 1 通の E メールで送信されます。

レポートセットを設定する手順については、 [レポートセットの操作](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). 特定の [!DNL Report.cfg] パラメータ， 「 [Report.cfg のパラメーター](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
