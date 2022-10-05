---
description: デフォルトのビジュアライゼーションを変更する手順です。
title: データセットスキーマインターフェイスの設定
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 46%

---

# データセットスキーマインターフェイスの設定{#configure-the-dataset-schema-interface}

{{eol}}

デフォルトのビジュアライゼーションを変更する手順です。

ビジュアライゼーションの種類を制御し、 [!DNL Dataset Schema Interface] ファイルをData Workbenchサーバーインストールフォルダーの Profiles\*profile name*\Context\Server LegendDimensionーに追加する。 このフォルダーにある [!DNL Default.1d] ファイルによって、すべてのディメンションのデフォルトのビジュアライゼーションのタイプが制御されます。このフォルダーに「*ディメンション名*. ファイル」（[!DNL Hour.1d].1d など）を追加して、その特定のディメンションのデフォルトのビジュアライゼーションを制御できます。

詳しくは、 [!DNL Dataset Schema Interfaces]を参照してください。 [データセットスキーマインターフェイス](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**デフォルトのビジュアライゼーションを変更するには**

1. 任意のワークスペースで、新しいデフォルトのビジュアライゼーションに表示するデータを含むビジュアライゼーションを作成します。

   例えば、横向き棒グラフでディメンションを表示する場合は、目的の指標およびディメンションを表示する横向き棒グラフのビジュアライゼーションを作成します。

1. 吹き出しウィンドウの上の枠を右クリックし、 **[!UICONTROL Save]**.
1. 内 [!DNL Save] ウィンドウ、クリック ![](assets/btn_folder_up.png)，ダブルクリック **[!UICONTROL Context]**&#x200B;をクリックし、ダブルクリックします。 **[!UICONTROL Dimension Legend]**.
1. 内 [!DNL File Name] 「 」フィールドに、ディメンション名を入力します。

   の名前 [!DNL .1d] ファイルは、ディメンションの名前と完全に一致する必要があります。 例：[!DNL Hour.1d]。

1. ファイル拡張子を「1d」に変更し、 **[!UICONTROL Save]**.

   ファイルは User\*working profile name*\Context\User Legend フォルダーにDimensionされます。

   次に [!DNL Dataset Schema Interface]に設定すると、指定したビジュアライゼーションが表示されます。

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. 内 [!DNL Profile Manager]をクリックし、 **[!UICONTROL Context]**&#x200B;を選択し、「 **[!UICONTROL Dimension Legend]**.

   1. 内の新しい引き出し線のファイル名の横にあるチェックマークを右クリックします。 [!DNL User] 列とクリック **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
