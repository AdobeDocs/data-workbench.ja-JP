---
description: 「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。
solution: Analytics
title: 設定オプション
topic: Data workbench
uuid: 1edfcf03-b278-4d81-942c-c9024378e13c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定オプション{#configuration-option}

「設定」オプションを選択すると Insight.cfg ファイルが開きます。このファイルは各種サーバーへの接続を制御します。

![](assets/cfg_Workstation.png)

**Insight.cfg ファイルを編集するには**

1. [!DNL Insight.cfg] ウィンドウで、必要に応じてパラメーターを変更します。ファイル内のパラメーターについて詳しくは、 [!DNL Insight.cfg] 『 [Insight設定パラメーター』を参照してください](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 設定を保存するには、ウィンドウ上部の **[!UICONTROL Insight.cfg (modified)]** を右クリックし、をクリックしま **[!UICONTROL Save as Insight.cfg]**&#x200B;す。

**新しいサーバーを追加するには**

1. ウィンドウ [!DNL Insight.cfg] で右クリックし、「>」 **[!UICONTROL Servers]** をクリッ **[!UICONTROL Add new child]** クしま **[!UICONTROL Server]**&#x200B;す。

   ![](assets/cfg_Workstation_AddServer.png)

1. 目的のサーバーへのアクセスをData Workbenchに提供するために、サーバーのパラメーターを入力または変更します。 ファイル内のパラメーターについて詳しくは、 [!DNL Insight.cfg] 『 [Insight設定パラメーター』を参照してください](../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b)。
1. 接続を設定するサーバーごとに手順 1 と 2 を繰り返します。
1. 設定を保存するには、ウィンドウ上部の **[!UICONTROL Insight.cfg (modified)]** を右クリックし、をクリックしま **[!UICONTROL Save as Insight.cfg]**&#x200B;す。

指定した設定を使用して、Data Workbenchがサーバーへの接続を試行します。 If a connection is established, a green node appears in the [!DNL Servers Manager] as shown below. Data Workbenchがサーバーに接続できない場合は、赤いノードが表示されます。

![](assets/vis_SysStat_RedGreenDots.png)

