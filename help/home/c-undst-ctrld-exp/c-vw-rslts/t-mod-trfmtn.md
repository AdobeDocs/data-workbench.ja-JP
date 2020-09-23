---
description: x-esprientフィールドが使用可能になったら、拡張ディメンションを作成して、x-esprientフィールドをデータセットに含める必要があります。これにより、Insightで結果を表示できます。
solution: Analytics,Analytics
title: Transformation.cfg の変更
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 6%

---


# Transformation.cfg の変更{#modifying-transformation-cfg}

x-esprientフィールドが使用可能になったら、拡張ディメンションを作成して、x-esprientフィールドをデータセットに含める必要があります。これにより、Insightで結果を表示できます。

これを行うには、新しいディメンションを [!DNL Transformation.cfg] ファイルに追加する必要があります。

複数の実験を行う場合は、新しいSplit変換を [!DNL Transformation.cfg] ファイルに追加する必要もあります。 このSplit変換は、異なるテスト名とグループ名を分離するので、情報の解釈がしやすくなります。 後で別の実験を追加する必要が生じた場合にデータの再処理を防ぐため、現在複数の実験を実行する予定がない場合でも、Split変換を追加することをAdobeにお勧めします。

次の手順では、新しいSplit変換と拡張ディメンションの両方を作成します。 Split変換を追加したくない場合は、手順5 ～ 7をスキップします。

**Transformation.cfgを変更するには**

1. で、ワ [!DNL Insight]ークスペース内で右クリックし、 [!DNL Profile Manager] >をクリックして、または **[!UICONTROL Admin]****[!UICONTROL Profile Manager]**[!DNL Admin] タブのプロファイル管理ワークスペースを開いて、を開きます。
1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]** to show its contents.
1. の横のチェックマークを右クリックし、 [!DNL Transformation.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** /をクリックし **[!UICONTROL in Insight]**&#x200B;ます。 The [!DNL Transformation.cfg] window appears.
1. **[!UICONTROL Transformation]** をクリックしてその内容を表示します。
1. 右クリック **[!UICONTROL Transformations]** し、「>」をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL Split]**&#x200B;す。
1. 次の例に示すように、コンマでの変換に対する新しい分割を行います。

   ![ステップ情報](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >「名前」フィールドには任意の値を入力できます。

1. 右クリック **[!UICONTROL Extended Dimensions]** し、「>」をクリックし **[!UICONTROL Add new]** ま **[!UICONTROL ManyToMany]**&#x200B;す。
1. 次の例に示すように、新しいディメンションを完成させます。

   ![ステップ情報](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 「名前」フィールドには任意の値を入力できます。
   >* Split変換を含めなかった場合は、 [!DNL Input] フィールドに「x-esprient」と入力する必要があります。


1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。
1. で、 [!DNL Profile Manager]列ののチェックマークを右クリックし、 [!DNL Transformation.cfg][!DNL User]**[!UICONTROL Save to]****[!UICONTROL profile name]** /をクリックして、作業プロファイルに対してローカルに適用した変更を保存します。

   >[!NOTE]
   >
   >データセットはすぐに再変換を開始します。

   For more information about [!DNL Transformation.cfg] and extended dimensions, see the *Dataset Configuration Guide*.
