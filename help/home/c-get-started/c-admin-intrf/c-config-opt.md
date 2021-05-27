---
description: 「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。
title: 設定オプション
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
exl-id: bb694d3c-64f7-4a74-b774-4d5145250e6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 35%

---

# 設定オプション{#configuration-option}

「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。

![](assets/cfg_Workstation.png)

**Insight.cfg ファイルを編集するには**

1. [!DNL Insight.cfg] ウィンドウで、必要に応じてパラメーターを変更します。[!DNL Insight.cfg]ファイル内のパラメーターについて詳しくは、「[Insight設定パラメーター](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)」を参照してください。
1. 設定を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL Insight.cfg (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save as Insight.cfg]**」をクリックします。

**新しいサーバーを追加するには**

1. [!DNL Insight.cfg]ウィンドウで&#x200B;**[!UICONTROL Servers]**&#x200B;を右クリックし、**[!UICONTROL Add new child]** / **[!UICONTROL Server]**&#x200B;をクリックします。

   ![](assets/cfg_Workstation_AddServer.png)

1. 目的のサーバーへのアクセス権をData Workbenchに与えるために、サーバーのパラメーターを入力または変更します。 [!DNL Insight.cfg]ファイル内のパラメーターについて詳しくは、「[Insight設定パラメーター](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)」を参照してください。
1. 接続を設定するサーバーごとに手順 1 と 2 を繰り返します。
1. 設定を保存するには、ウィンドウ上部の&#x200B;**[!UICONTROL Insight.cfg (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save as Insight.cfg]**」をクリックします。

Data Workbenchは、指定した設定を使用してサーバーへの接続を試みます。 接続が確立されると、次に示すように、[!DNL Servers Manager]に緑のノードが表示されます。 Data Workbenchがサーバーに接続できない場合は、赤いノードが表示されます。

![](assets/vis_SysStat_RedGreenDots.png)
