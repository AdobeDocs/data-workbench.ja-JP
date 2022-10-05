---
description: Log Processing.cfg ファイルに x-experiment フィールドを追加する必要があります。このフィールドは、拡張ディメンションの作成に使用されます。
solution: Analytics
title: Log Processing.cfg の変更
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 12%

---

# Log Processing.cfg の変更{#modifying-log-processing-cfg}

{{eol}}

Log Processing.cfg ファイルに x-experiment フィールドを追加する必要があります。このフィールドは、拡張ディメンションの作成に使用されます。

詳しくは、 [Transformation.cfg の変更](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Log Processing.cfg を変更するには、以下を実行します。**

1. In [!DNL Insight]、 [!DNL Profile Manager] ワークスペース内で右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**&#x200B;または、 [!DNL Admin] タブをクリックします。
1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Dataset]** 内容を表示する。
1. の横のチェックマークを右クリックします。 [!DNL Log Processing.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. この [!DNL Log Processing.cfg] ウィンドウが表示されます。
1. **[!UICONTROL Fields]** をクリックしてその内容を表示します。
1. 現在のリストの最後のフィールドを右クリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. 次の例に示すように、新しく作成したフィールドに x-experiment と入力します。

   ![ステップ情報](assets/logprocessing.png)

1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL Log Processing.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* をクリックして、作業プロファイルに対してローカルで行った変更を保存します。

   >[!NOTE]
   >
   >データセットの再処理は直ちに開始されます。

   ログ処理とフィールドについて詳しくは、 *データセット設定ガイド*.
