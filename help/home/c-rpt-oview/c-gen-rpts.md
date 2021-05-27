---
description: ワークスペースを処理し、レポートとして指定して、レポートを生成します。
title: レポートの生成
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# レポートの生成{#generating-reports}

ワークスペースを処理し、レポートとして指定して、レポートを生成します。

[!DNL Report] は、ファイルのパラメーターで設定された間隔(「 [!DNL Every] 」など)で、レポートを日単位で処理するレポートを、その他のファイル設定に基づいてレポートを生 [!DNL Report.cfg]  [!DNL "day] [!DNL Report.cfg] 成します。

レポートを生成する際、完了率は、そのレポートのサムネールの下の「[!DNL Reports]」タブに表示されます。 レポートの生成中に[!DNL Report]で問題が発生した場合は、レポートセットのフォルダーの「[!DNL Reports]」タブに最新のエラーメッセージが表示されます。 [!DNL Report]が特定のレポートに対してエラーが発生した場合は、セット内の他のレポートも引き続き処理されます。

[!DNL Report.cfg]ファイル内の[!DNL Report Types]パラメーターを使用して、次の形式またはすべての形式でレポートセットにレポートを生成できます。

* Microsoft Excelファイル（[!DNL .xls]または[!DNL .xlsx]）
* ポータブルネットワークグラフィックファイル([!DNL .png])
* サムネール([!DNL .jpg])

指定した出力タイプと共に、[!DNL Report]はレポートと同じ名前の[!DNL .xml]ファイルを作成します。 この&#x200B;*`<report name>`*.xmlファイルには、レポートのサムネールの下の[!DNL Reports]タブにData Workbenchで表示されるレポートの説明が含まれています。 これにより、レポートポータルを通じてレポートを配信する際に説明が使用できるようになります。 [!DNL Report Portal]について詳しくは、[Report Portalの操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)を参照してください。

>[!NOTE]
>
>内部指標を再定義すると、誤った値が原因でシステムが予期せず動作します。 指標が 100% 読み取られない限り、レポートは生成されません。指標の定義を変更しないことをお勧めします。
