---
description: 拡張ディメンションの作成に使用するLog Processing.cfgファイルにx-experientフィールドを追加する必要があります。
solution: Analytics,Analytics
title: Log Processing.cfg の変更
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 12%

---


# Log Processing.cfg の変更{#modifying-log-processing-cfg}

拡張ディメンションの作成に使用するLog Processing.cfgファイルにx-experientフィールドを追加する必要があります。

Transformation.cfgの [変更を参照してください](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**Log Processing.cfgを変更するには**

1. で、ワ [!DNL Insight]ークスペース内で右クリックし、 [!DNL Profile Manager] >をクリックして、または **[!UICONTROL Admin]****[!UICONTROL Profile Manager]**[!DNL Admin] タブのプロファイル管理ワークスペースを開いて、を開きます。
1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]** to show its contents.
1. の横のチェックマークを右クリックし、 [!DNL Log Processing.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** /をクリックし **[!UICONTROL in Insight]**&#x200B;ます。 The [!DNL Log Processing.cfg] window appears.
1. **[!UICONTROL Fields]** をクリックしてその内容を表示します。
1. 現在のリストの最後のフィールドを右クリックし、 **[!UICONTROL Add new]** /をクリックし **[!UICONTROL Field]**&#x200B;ます。
1. 次の例に示すように、新しく作成されたフィールドにx-esprientと入力します。

   ![ステップ情報](assets/logprocessing.png)

1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。
1. で、 [!DNL Profile Manager]列ののチェックマークを右クリックし、 [!DNL Log Processing.cfg] / [!DNL User] &lt; **[!UICONTROL Save to]*****[!UICONTROL profile name]*** >をクリックして、作業プロファイルに対してローカルに適用した変更を保存します。

   >[!NOTE]
   >
   >データセットはすぐに再処理を開始します。

   ログ処理とフィールドについて詳しくは、『 *データセット設定ガイド*』を参照してください。

