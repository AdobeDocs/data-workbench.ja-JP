---
description: 拡張ディメンションの作成に使用するLog Processing.cfgファイルにx-experientフィールドを追加する必要があります。
solution: Insight,Analytics
title: Log Processing.cfgの変更
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Log Processing.cfgの変更{#modifying-log-processing-cfg}

拡張ディメンションの作成に使用するLog Processing.cfgファイルにx-experientフィールドを追加する必要があります。

Transformation.cfg [の変更を参照してください](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**Log Processing.cfgを変更するには**

1. で、ワー [!DNL Insight]クスペース内 [!DNL Profile Manager] で右クリックし、/をクリックするか、 **[!UICONTROL Admin]** タ **[!UICONTROL Profile Manager]**&#x200B;ブのプロファイル管理ワークスペースを開き [!DNL Admin] ます。
1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]** to show its contents.
1. の横のチェックマークを右クリックし、をク [!DNL Log Processing.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Insight]**&#x200B;す。 The [!DNL Log Processing.cfg] window appears.
1. **[!UICONTROL Fields]** をクリックしてその内容を表示します。
1. 現在のリストの最後のフィールドを右クリックし、/をクリッ **[!UICONTROL Add new]** クしま **[!UICONTROL Field]**&#x200B;す。
1. 次の例に示すように、新しく作成したフィールドにx-esteptと入力します。

   ![ステップ情報](assets/logprocessing.png)

1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
1. で、列 [!DNL Profile Manager]のチェックマークを右クリックし、 [!DNL Log Processing.cfg] / [!DNL User] &lt; **[!UICONTROL Save to]** >をクリックして、作業プロファイルに対してローカルに適用した変更を保存します ***[!UICONTROL profile name]*** 。

   >[!NOTE]
   >
   >データセットはすぐに再処理を開始します。

   ログ処理とフィールドについて詳しくは、『データセット設定ガイド』 *を参照してください*。

