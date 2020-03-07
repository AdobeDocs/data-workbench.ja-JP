---
description: ワークスペースを処理し、レポートとして指定して、レポートを生成します。
solution: Analytics
title: レポートの生成
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# レポートの生成{#generating-reports}

ワークスペースを処理し、レポートとして指定して、レポートを生成します。

[!DNL Report] ファイル内のパラメータで設定された間 [!DNL Every] 隔（毎日レポートを処理する「」など）で、他のファイル設定に基づいてレポートを生成 [!DNL Report.cfg][!DNL "day][!DNL Report.cfg] します。

レポートの生成時に、完了率がそのレポートのサムネ [!DNL Reports] ールの下のタブに表示されます。 レポー [!DNL Report] トの生成中に問題が発生した場合は、レポートセットのフォルダー内のタ [!DNL Reports] ブに最新のエラーメッセージが表示されます。 特定の [!DNL Report] レポートでエラーが発生した場合、セット内の他のレポートも引き続き処理されます。

ファイル内のパラメーターを使用して、次のいずれかまたはすべての形式でレポートセット内のレポー [!DNL Report Types] トを生成で [!DNL Report.cfg] きます。

* Microsoft Excelファイル(ま [!DNL .xls] たは [!DNL .xlsx])
* ポータブルネットワークグラフィックファ [!DNL .png]イル()
* サムネール( [!DNL .jpg])

指定した出力のタイプと共に、レポート [!DNL Report] と同じ名前 [!DNL .xml] のファイルが作成されます。 この *`<report name>`*.xmlファイルには、レポートのサムネールの下のタブにあるData Workbenchに表示さ [!DNL Reports] れるレポートの説明が含まれています。 これにより、レポートポータルを通じてレポートを配信する際に説明を使用できるようになります。 について詳しくは、「レポー [!DNL Report Portal]トポータル [の使用」を参照してください](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>内部指標を再定義すると、誤った値が原因でシステムが予期せず動作します。 指標が100%でない限り、レポートは生成されません。 指標の定義は変更しないことをお勧めします。
