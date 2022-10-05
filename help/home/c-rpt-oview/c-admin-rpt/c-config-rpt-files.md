---
description: Report Portal では、Report Server で生成されたレポートを Excel ファイル（.xls または.xlsx）または.png ファイルとして表示できます。
title: Report.cfg ファイルの設定
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# Report.cfg ファイルの設定{#configuring-report-cfg-files}

{{eol}}

Report Portal では、Report Server で生成されたレポートを Excel ファイル（.xls または.xlsx）または.png ファイルとして表示できます。

レポートセットを [!DNL Report Portal]を使用する場合、 [!DNL Report.cfg] ファイルに含める必要があります。

* 内 **[!UICONTROL Output Root]** パラメーターを指定し、ポータルに使用する web サーバーのドキュメントルートを指定します。
* 内 **[!UICONTROL Report Types]** パラメーターを使用する場合は、生成するレポートタイプとして、Excel、png またはサムネールを指定します。

条件 [!DNL Report Server] 指定した形式でレポートが生成され、Web サーバーのドキュメントルートにこれらのファイルが配置されます。このルートは、インストール時に [!DNL Report Portal] をクリックして、レポートにアクセスします。

特定の [!DNL Report.cfg] パラメータ， 「 [Report.cfg のパラメーター](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
