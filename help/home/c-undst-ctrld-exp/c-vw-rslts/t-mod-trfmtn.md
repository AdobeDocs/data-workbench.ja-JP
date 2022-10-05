---
description: x-experiment フィールドを使用できるようになったら、拡張ディメンションを作成して、x-experiment フィールドをデータセットに含める必要があります。これにより、Insight で結果を表示できます。
solution: Analytics
title: Transformation.cfg の変更
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 6%

---

# Transformation.cfg の変更{#modifying-transformation-cfg}

{{eol}}

x-experiment フィールドを使用できるようになったら、拡張ディメンションを作成して、x-experiment フィールドをデータセットに含める必要があります。これにより、Insight で結果を表示できます。

これをおこなうには、新しいディメンションを [!DNL Transformation.cfg] ファイル。

複数の実験を実行する場合は、新しい分割変換を [!DNL Transformation.cfg] ファイル。 この分割変換は、異なる実験名とグループ名を分離し、情報が解釈しやすくします。 後から実験を追加する必要が生じた場合にデータの再処理を避けるために、現在複数の実験を実行する予定がない場合でも、 Split 変換を追加することをお勧めします。

以下の手順では、新しい Split 変換と拡張ディメンションの両方を作成します。 Split 変換を追加しない場合は、手順 5 ～ 7 をスキップします。

**Transformation.cfg を変更するには、以下を実行します。**

1. In [!DNL Insight]、 [!DNL Profile Manager] ワークスペース内で右クリックし、 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**&#x200B;または、 [!DNL Admin] タブをクリックします。
1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Dataset]** 内容を表示する。
1. の横のチェックマークを右クリックします。 [!DNL Transformation.cfg] をクリックし、 **[!UICONTROL Make Local]**. このファイル用のチェックマークが [!DNL User] 列に表示されます。
1. 新しく作成されたチェックマークを右クリックし、 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. この [!DNL Transformation.cfg] ウィンドウが表示されます。
1. **[!UICONTROL Transformation]** をクリックしてその内容を表示します。
1. 右クリック **[!UICONTROL Transformations]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. 次の例に示すように、コンマ変換で新しい分割を完了します。

   ![ステップ情報](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >「名前」フィールドには任意の値を入力できます。

1. 右クリック **[!UICONTROL Extended Dimensions]** をクリックし、 **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. 次の例に示すように、新しいディメンションを入力します。

   ![ステップ情報](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* 「名前」フィールドには任意の値を入力できます。
   >* Split 変換を含めなかった場合は、「x-experiment」と [!DNL Input] フィールドに入力します。


1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.
1. 内 [!DNL Profile Manager]、次のチェックマークを右クリック： [!DNL Transformation.cfg] 内 [!DNL User] 列、「 **[!UICONTROL Save to]** > **[!UICONTROL profile name]** をクリックして、作業プロファイルに対してローカルで行った変更を保存します。

   >[!NOTE]
   >
   >データセットの再変換は直ちに開始されます。

   詳しくは、 [!DNL Transformation.cfg] 拡張ディメンションについては、 *データセット設定ガイド*.
