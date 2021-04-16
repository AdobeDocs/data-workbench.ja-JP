---
description: ワークスペースを処理し、レポートとして指定してレポートを生成します。
title: レポートの生成
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# レポートの生成{#generating-reports}

ワークスペースを処理し、レポートとして指定してレポートを生成します。

[!DNL Report] ファイル内の [!DNL Every] パラメーターに設定された間隔( [!DNL Report.cfg] ファイル内のレポートを毎日処理する「 [!DNL "day]」など)で、他の [!DNL Report.cfg] ファイル設定に基づいてレポートを生成します。

レポートの生成時に、完了率がそのレポートのサムネールの下の[!DNL Reports]タブに表示されます。 レポートの生成中に[!DNL Report]で問題が発生した場合は、最新のエラーメッセージがレポートセットのフォルダー内の[!DNL Reports]タブに表示されます。 [!DNL Report]が特定のレポートに対してエラーを検出した場合、セット内の他のレポートも引き続き処理されます。

[!DNL Report.cfg]ファイルの[!DNL Report Types]パラメーターを使用して、次の形式のレポートセット内でレポートを生成できます。

* Microsoft Excelファイル（[!DNL .xls]または[!DNL .xlsx]）
* ポータブルネットワークグラフィックファイル([!DNL .png])
* サムネール([!DNL .jpg])

[!DNL Report]は、指定された出力タイプと共に、レポートと同じ名前の[!DNL .xml]ファイルを作成します。 この&#x200B;*`<report name>`*.xmlファイルには、レポートのサムネールの下の[!DNL Reports]タブにData Workbenchして表示されるレポートの説明が含まれています。 これにより、レポートポータル経由でレポートを配信する際に説明が使用できるようになります。 [!DNL Report Portal]について詳しくは、[レポートポータルの操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)を参照してください。

>[!NOTE]
>
>内部指標を再定義すると、誤った値が原因でシステムが予期せず動作します。 指標が 100% 読み取られない限り、レポートは生成されません。指標の定義を変更しないことをお勧めします。
