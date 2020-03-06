---
description: デフォルトのビジュアライゼーションを変更する手順です。
solution: Analytics
title: データセットスキーマインターフェイスの設定
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configure the Dataset Schema Interface{#configure-the-dataset-schema-interface}

デフォルトのビジュアライゼーションを変更する手順です。

You can control which type of visualization displays when you click a dimension name in a [!DNL Dataset Schema Interface] by adding files to the Profiles\*profile name*\Context\Dimension Legend folder of the Data Workbench server installation folder. このフォルダーにある [!DNL Default.1d] ファイルによって、すべてのディメンションのデフォルトのビジュアライゼーションのタイプが制御されます。このフォルダーに「*ディメンション名*. ファイル」（[!DNL Hour.1d].1d など）を追加して、その特定のディメンションのデフォルトのビジュアライゼーションを制御できます。

詳しくは、「データセットスキ [!DNL Dataset Schema Interfaces]ーマインタ [ーフェイス」を参照してくださ](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)い。

**デフォルトのビジュアライゼーションを変更するには**

1. 任意のワークスペースで、新しいデフォルトのビジュアライゼーションに表示するデータを含むビジュアライゼーションを作成します。

   例えば、横向き棒グラフでディメンションを表示する場合は、目的の指標およびディメンションを表示する横向き棒グラフのビジュアライゼーションを作成します。

1. Right-click the top border of the callout window and click **[!UICONTROL Save]**.
1. In the [!DNL Save] window, click ![](assets/btn_folder_up.png), double-click **[!UICONTROL Context]**, then double-click **[!UICONTROL Dimension Legend]**.
1. In the [!DNL File Name] field, type the dimension name.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. 例：[!DNL Hour.1d]。

1. Change the file extension to “1d” and click **[!UICONTROL Save]**.

   ファイルはUser\*working profile name*\Context\Dimension Legend folderに保存されます。

   The next time that you click that dimension from in a [!DNL Dataset Schema Interface], the visualization that you specified displays.

1. （オプション）この変更を作業プロファイルのすべてのユーザーが利用できるようにするには、次のようにします。

   1. で、をクリ [!DNL Profile Manager]ックし、を **[!UICONTROL Context]**&#x200B;クリックしま **[!UICONTROL Dimension Legend]**&#x200B;す。

   1. Right-click the check mark next to the file name of the new callout in the [!DNL User] column and click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

