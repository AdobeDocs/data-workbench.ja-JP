---
description: 「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。
title: 設定オプション
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 35%

---

# 設定オプション{#configuration-option}

{{eol}}

「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。

![](assets/cfg_Workstation.png)

**Insight.cfg ファイルを編集するには**

1. [!DNL Insight.cfg] ウィンドウで、必要に応じてパラメーターを変更します。詳しくは、 [!DNL Insight.cfg] ファイル： [Insight 設定パラメーター](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. 設定を保存するには、右クリックします。 **[!UICONTROL Insight.cfg (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save as Insight.cfg]**.

**新しいサーバーを追加するには**

1. 内 [!DNL Insight.cfg] ウィンドウ、右クリック **[!UICONTROL Servers]** をクリックし、 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddServer.png)

1. サーバーのパラメーターを入力または変更して、Data Workbenchが目的のサーバーにアクセスできるようにします。 詳しくは、 [!DNL Insight.cfg] ファイル： [Insight 設定パラメーター](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b).
1. 接続を設定するサーバーごとに手順 1 と 2 を繰り返します。
1. 設定を保存するには、右クリックします。 **[!UICONTROL Insight.cfg (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save as Insight.cfg]**.

Data Workbenchは、指定した設定を使用してサーバーへの接続を試みます。 接続が確立されると、緑のノードが [!DNL Servers Manager] 以下に示すように。 Data Workbenchがサーバーに接続できない場合は、赤いノードが表示されます。

![](assets/vis_SysStat_RedGreenDots.png)
