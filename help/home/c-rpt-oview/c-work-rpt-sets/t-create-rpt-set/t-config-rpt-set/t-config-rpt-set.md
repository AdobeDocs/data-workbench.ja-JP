---
description: ワークスペースを作成してレポートセットフォルダーに保存した後、新しい Report.cfg ファイルを作成する必要があります。
title: レポートセットの設定
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# レポートセットの設定{#configure-the-report-set}

{{eol}}

ワークスペースを作成してレポートセットフォルダーに保存した後、新しい Report.cfg ファイルを作成する必要があります。

を [!DNL Report.cfg] レポートを生成し、配布するタイミングと方法を示すレポートセット用のファイル。

**新しい Report.cfg を作成するには、以下を実行します。**

1. Data Workbench で、 [!DNL Profile Manager] ワークスペース内で右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Profile]** > **[!UICONTROL Profile Manager]**.
1. クリック **[!UICONTROL Reports]** 開く [!DNL Reports] フォルダー。
1. レポートセットのフォルダーをクリックします。
1. 内 [!DNL User] 列を右クリックし、 **[!UICONTROL Create]** > **[!UICONTROL Report]**. 新しい [!DNL Report.cfg] ファイルが [!DNL File]列。
1. 内 [!DNL User] 新しい [!DNL Report.cfg] ファイルを開き、 [!DNL Report.cfg] ファイルを選択し、 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   ![ステップ情報](assets/cfg_reportcfg.png)

1. 必要に応じて設定パラメーターを編集します。 これらのパラメーターについて詳しくは、 [Report.cfg のパラメーター](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

   >[!NOTE]
   >
   >サンプル [!DNL Report.cfg] この例では、 [!DNL Report.cfg] ファイルに書き込まれます。 追加のパラメーターを [!DNL Report.cfg] ファイルに書き込む場合は、テキストエディターを使用する必要があります。 その手順については、 [既存の Report.cfg ファイルの編集](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

1. 右クリックしてファイルを保存 **[!UICONTROL Report.cfg (modified)]** をクリックして、 **[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]**>***[!UICONTROL \Report.cfg]**.
1. ファイルを閉じます。
1. 内 [!DNL Profile Manager]を選択し、 [!DNL User] 新しい [!DNL Report.cfg] ファイルと選択 **[!UICONTROL Save to]***&lt; **[!UICONTROL profile name]**>*.
