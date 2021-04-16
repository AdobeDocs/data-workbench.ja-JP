---
description: ワークスペースを作成してレポートセットフォルダーに保存した後、新しいReport.cfgファイルを作成する必要があります。
title: レポートセットの設定
uuid: 21f8dcde-8fe1-4ba0-9eb7-39ff812dcf14
exl-id: 780e6bb1-b332-4984-b132-df11d95b592a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# レポートセットの設定{#configure-the-report-set}

ワークスペースを作成してレポートセットフォルダーに保存した後、新しいReport.cfgファイルを作成する必要があります。

レポートを生成および配布するタイミングと方法をレポートセットの[!DNL Report.cfg]ファイルに指定する必要があります。

**新しいReport.cfgを作成するには**

1. data workbenchで、ワークスペース内で右クリックし、**[!UICONTROL Admin]**/**[!UICONTROL Profile]**/**[!UICONTROL Profile Manager]**&#x200B;をクリックして、[!DNL Profile Manager]を開きます。
1. **[!UICONTROL Reports]**&#x200B;をクリックして[!DNL Reports]フォルダーを開きます。
1. レポートセットのフォルダをクリックします。
1. レポートセットフォルダーの[!DNL User]列で右クリックし、**[!UICONTROL Create]**/**[!UICONTROL Report]**&#x200B;を選択します。 新しい[!DNL Report.cfg]ファイルが[!DNL File]列に表示されます。
1. 新しい[!DNL Report.cfg]ファイルの[!DNL User]列で、[!DNL Report.cfg]ファイルのチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL from the workbench]**&#x200B;をクリックします。

   ![ステップ情報](assets/cfg_reportcfg.png)

1. 必要に応じて、設定パラメーターを編集します。 これらのパラメーターについて詳しくは、[Report.cfgパラメーター](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)を参照してください。

   >[!NOTE]
   >
   >この例のサンプル[!DNL Report.cfg]には、デフォルトで[!DNL Report.cfg]ファイルに含まれているパラメーターのみが含まれています。 [!DNL Report.cfg]ファイルにパラメーターを追加する必要がある場合は、テキストエディターを使用して追加する必要があります。 そのための手順については、[既存のReport.cfgファイルの編集](../../../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)を参照してください。

1. ファイルの上部の&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save as Reports\]***&lt; **[!UICONTROL ReportSetName]*****[!UICONTROL \Report.cfg]**をクリックして、ファイルを保存します。
1. ファイルを閉じます。
1. [!DNL Profile Manager]で、新しい[!DNL Report.cfg]ファイルの[!DNL User]列のチェックマークを右クリックし、**[!UICONTROL Save to]*****[!UICONTROL profile name]***を選択します。
