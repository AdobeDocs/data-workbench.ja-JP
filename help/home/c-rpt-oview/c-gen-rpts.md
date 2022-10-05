---
description: ワークスペースを処理し、レポートとして指定して、レポートを生成します。
title: レポートの生成
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# レポートの生成{#generating-reports}

{{eol}}

ワークスペースを処理し、レポートとして指定して、レポートを生成します。

[!DNL Report] は、 [!DNL Every] パラメーター [!DNL Report.cfg] ファイル ( [!DNL "day]」で始まり、他の [!DNL Report.cfg] ファイル設定。

レポートを生成する際に、完了率が [!DNL Reports] 」タブをクリックします。 If [!DNL Report] レポートの生成中に問題が発生した場合、最新のエラーメッセージが [!DNL Reports] 」タブをクリックします。 If [!DNL Report] は特定のレポートに対してエラーを検出し、セット内の他のレポートを引き続き処理します。

レポートは、以下の書式のいずれかまたはすべてで、 [!DNL Report Types] パラメーター [!DNL Report.cfg] ファイル：

* Microsoft Excel ファイル ( [!DNL .xls] または [!DNL .xlsx])
* ポータブルネットワークグラフィックファイル ( [!DNL .png])
* サムネール ( [!DNL .jpg])

指定した出力のタイプと共に、 [!DNL Report] を作成 [!DNL .xml] ファイルの名前は、レポートと同じです。 この *`<report name>`*.xml ファイルには、 [!DNL Reports] 」タブをクリックします。 これにより、レポートポータルを通じてレポートを配信する際に、説明を使用できるようになります。 詳しくは、 [!DNL Report Portal]を参照してください。 [Report Portal の操作](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>内部指標を再定義すると、誤った値が原因でシステムが予期せず動作します。 指標が 100% 読み取られない限り、レポートは生成されません。指標の定義を変更しないことをお勧めします。
