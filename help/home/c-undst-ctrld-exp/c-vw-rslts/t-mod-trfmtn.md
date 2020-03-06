---
description: x-esperientフィールドが使用可能になったら、拡張ディメンションを作成して、x-experientフィールドをデータセットに含め、Insightで結果を表示できるようにする必要があります。
solution: Insight,Analytics
title: Transformation.cfgの変更
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Transformation.cfgの変更{#modifying-transformation-cfg}

x-esperientフィールドが使用可能になったら、拡張ディメンションを作成して、x-experientフィールドをデータセットに含め、Insightで結果を表示できるようにする必要があります。

これを行うには、新しいディメンションをファイルに追加する必要があ [!DNL Transformation.cfg] ります。

複数の実験を行う場合は、新しいSplit変換もファイルに追加する必要があり [!DNL Transformation.cfg] ます。 このSplit変換は、情報を解釈しやすくするために、異なるテスト名とグループ名を分離します。 後で別の実験を追加する必要が生じた場合にデータの再処理を避けるため、複数の実験を実行する予定がない場合でも、Split変換を追加することをお勧めします。

次の手順では、新しいSplit変換と拡張ディメンションの両方を作成します。 Split変換を追加しない場合は、手順5 ～ 7をスキップします。

**Transformation.cfgを変更するには**

1. で、ワー [!DNL Insight]クスペース内 [!DNL Profile Manager] で右クリックし、/をクリックするか、 **[!UICONTROL Admin]** タ **[!UICONTROL Profile Manager]**&#x200B;ブのプロファイル管理ワークスペースを開き [!DNL Admin] ます。
1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]** to show its contents.
1. の横のチェックマークを右クリックし、をク [!DNL Transformation.cfg] リックしま **[!UICONTROL Make Local]**&#x200B;す。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、/をクリ **[!UICONTROL Open]** ックしま **[!UICONTROL in Insight]**&#x200B;す。 The [!DNL Transformation.cfg] window appears.
1. **[!UICONTROL Transformation]** をクリックしてその内容を表示します。
1. 右クリックし、/ **[!UICONTROL Transformations]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL Split]**&#x200B;す。
1. 次の例に示すように、コンマでの新しい分割変換を完了します。

   ![ステップ情報](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >「名前」フィールドには任意の値を入力できます。

1. 右クリックし、/ **[!UICONTROL Extended Dimensions]** をクリ **[!UICONTROL Add new]** ックしま **[!UICONTROL ManyToMany]**&#x200B;す。
1. 次の例に示すように、新しいディメンションを完成させます。

   ![ステップ情報](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 「名前」フィールドには任意の値を入力できます。
   >* Split変換を含めなかった場合は、フィールドに「x-tesprient」と入力する必要があり [!DNL Input] ます。


1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。
1. で、列 [!DNL Profile Manager]ののチェックマークを右クリックし、「/」をクリッ [!DNL Transformation.cfg] クして、作業プロファイルに対してロ [!DNL User] ーカ **[!UICONTROL Save to]****[!UICONTROL profile name]** ルに適用した変更を保存します。

   >[!NOTE]
   >
   >データセットはすぐに再変換を開始します。

   For more information about [!DNL Transformation.cfg] and extended dimensions, see the *Dataset Configuration Guide*.
