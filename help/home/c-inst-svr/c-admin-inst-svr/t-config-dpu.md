---
description: DPU設定ファイルDPU.cfgは、Insight Serverの様々なパフォーマンスパラメーターを指定します。
solution: Analytics
title: DPU.cfg の設定
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---


# DPU.cfg の設定{#configuring-dpu-cfg}

DPU設定ファイルDPU.cfgは、Insight Serverの様々なパフォーマンスパラメーターを指定します。

これらのパラメーターの設定方法は、データセットのサイズやその他の多くの要因に応じて異なります。 パフォーマンスの調整については、Adobeのコンサルティングサービスにお問い合わせください。

**推奨頻度：** 必要な場合のみ

**DPUパフォーマンス設定を変更するには[!DNL Insight Server]**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL DPU.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL DPU.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL DPU.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL DPU.cfg] window, click component to view its contents.
1. 必要に応じて、パフォーマンスとパスの設定を変更します。 このファイルで使用できるパラメーターのリストについては、 [DPUパフォーマンス設定を参照してください](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >このファイル内のパラメーターを変更する前に、Adobeにお問い合わせください。

   ![](assets/cfg_DPU_egvalues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

