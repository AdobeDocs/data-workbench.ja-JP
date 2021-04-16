---
description: x-esprientフィールドが使用可能になったら、拡張ディメンションを作成して、x-esprientフィールドをデータセットに含める必要があります。これにより、Insightで結果を表示できます。
solution: Analytics,Analytics
title: Transformation.cfg の変更
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 6%

---

# Transformation.cfg の変更{#modifying-transformation-cfg}

x-esprientフィールドが使用可能になったら、拡張ディメンションを作成して、x-esprientフィールドをデータセットに含める必要があります。これにより、Insightで結果を表示できます。

これを行うには、[!DNL Transformation.cfg]ファイルに新しいディメンションを追加する必要があります。

複数の実験を行う場合は、新しいSplit変換を[!DNL Transformation.cfg]ファイルに追加する必要もあります。 このSplit変換は、異なるテスト名とグループ名を分離するので、情報の解釈がしやすくなります。 後で別の実験を追加する必要が生じた場合にデータの再処理を防ぐため、現在複数の実験を実行する予定がない場合でも、Split変換を追加することをAdobeにお勧めします。

次の手順では、新しいSplit変換と拡張ディメンションの両方を作成します。 Split変換を追加したくない場合は、手順5 ～ 7をスキップします。

**Transformation.cfgを変更するには**

1. [!DNL Insight]で、ワークスペース内で右クリックし、**[!UICONTROL Admin]**/**[!UICONTROL Profile Manager]**&#x200B;をクリックするか、[!DNL Admin]タブのプロファイル管理ワークスペースを開いて、[!DNL Profile Manager]を開きます。
1. [!DNL Profile Manager]の&#x200B;**[!UICONTROL Dataset]**&#x200B;をクリックして、内容を表示します。
1. [!DNL Transformation.cfg]の横のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。 [!DNL Transformation.cfg]ウィンドウが表示されます。
1. **[!UICONTROL Transformation]** をクリックしてその内容を表示します。
1. **[!UICONTROL Transformations]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL Split]**&#x200B;をクリックします。
1. 次の例に示すように、コンマでの変換に対する新しい分割を行います。

   ![ステップ情報](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >「名前」フィールドには任意の値を入力できます。

1. **[!UICONTROL Extended Dimensions]**&#x200B;を右クリックし、**[!UICONTROL Add new]**/**[!UICONTROL ManyToMany]**&#x200B;をクリックします。
1. 次の例に示すように、新しいディメンションを完成させます。

   ![ステップ情報](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 「名前」フィールドには任意の値を入力できます。
   >* Split変換を含めなかった場合は、[!DNL Input]フィールドに「x-esprient」と入力する必要があります。


1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。
1. [!DNL Profile Manager]で、[!DNL User]列の[!DNL Transformation.cfg]のチェックマークを右クリックし、**[!UICONTROL Save to]**/**[!UICONTROL profile name]**&#x200B;をクリックして、作業プロファイルに対してローカルに適用した変更を保存します。

   >[!NOTE]
   >
   >データセットはすぐに再変換を開始します。

   [!DNL Transformation.cfg]と拡張ディメンションについて詳しくは、『*データセット設定ガイド*』を参照してください。
