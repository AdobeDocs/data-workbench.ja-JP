---
description: デフォルトのビジュアライゼーションを変更する手順です。
title: データセットスキーマインターフェイスの設定
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 46%

---

# データセットスキーマインターフェイスの設定{#configure-the-dataset-schema-interface}

デフォルトのビジュアライゼーションを変更する手順です。

プロファイル\*profile name*\Context\Dimension Legend folder of the Data Workbench server installation folderにファイルを追加することで、[!DNL Dataset Schema Interface]でディメンション名をクリックしたときに表示されるビジュアライゼーションのタイプを制御できます。 このフォルダーにある [!DNL Default.1d] ファイルによって、すべてのディメンションのデフォルトのビジュアライゼーションのタイプが制御されます。このフォルダーに「*ディメンション名*. ファイル」（[!DNL Hour.1d].1d など）を追加して、その特定のディメンションのデフォルトのビジュアライゼーションを制御できます。

[!DNL Dataset Schema Interfaces]について詳しくは、[データセットスキーマインターフェイス](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)を参照してください。

**デフォルトのビジュアライゼーションを変更するには**

1. 任意のワークスペースで、新しいデフォルトのビジュアライゼーションに表示するデータを含むビジュアライゼーションを作成します。

   例えば、横向き棒グラフでディメンションを表示する場合は、目的の指標およびディメンションを表示する横向き棒グラフのビジュアライゼーションを作成します。

1. 引き出し線ウィンドウの上の枠を右クリックし、「**[!UICONTROL Save]**」をクリックします。
1. [!DNL Save]ウィンドウで「![](assets/btn_folder_up.png)」をクリックし、「**[!UICONTROL Context]**」をダブルクリックしてから、「**[!UICONTROL Dimension Legend]**」をダブルクリックします。
1. [!DNL File Name]フィールドに、ディメンション名を入力します。

   [!DNL .1d]ファイルの名前は、ディメンションの名前と完全に一致する必要があります。 例：[!DNL Hour.1d]。

1. ファイル拡張子を「1d」に変更し、「**[!UICONTROL Save]**」をクリックします。

   ファイルは、User\*working profile name*\Context\Dimension Legend folderフォルダーに保存されます。

   次に[!DNL Dataset Schema Interface]でそのディメンションをクリックすると、指定したビジュアライゼーションが表示されます。

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. [!DNL Profile Manager]で「**[!UICONTROL Context]**」をクリックし、「**[!UICONTROL Dimension Legend]**」をクリックします。

   1. [!DNL User]列で、新しい引き出し線のファイル名の横にあるチェックマークを右クリックし、**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*&#x200B;をクリックします。
