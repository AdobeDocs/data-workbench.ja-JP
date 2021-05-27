---
description: DPU設定ファイルDPU.cfgは、Insightサーバーの様々なパフォーマンスパラメーターを指定します。
title: DPU.cfg の設定
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# DPU.cfg の設定{#configuring-dpu-cfg}

DPU設定ファイルDPU.cfgは、Insightサーバーの様々なパフォーマンスパラメーターを指定します。

これらのパラメーターの設定方法は、データセットのサイズやその他の多くの要因によって異なります。 パフォーマンスの調整については、Adobeコンサルティングサービスにお問い合わせください。

**推奨頻度：** 必要な場合のみ

**DPUパフォーマンス設 [!DNL Insight Server] 定を変更するには**

1. [!DNL Insight]の「[!DNL Admin] > [!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして「サーバーマネージャー」ワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]で、**[!UICONTROL Components]**&#x200B;をクリックして内容を表示します。 [!DNL DPU.cfg] ファイルは、このディレクトリ内に格納されています。
1. *[!DNL DPU.cfg]のサーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL DPU.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]** / **[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL DPU.cfg]ウィンドウで、「component」をクリックして内容を表示します。
1. 必要に応じて、パフォーマンスとパスの設定を変更します。 このファイルで使用できるパラメーターの一覧については、[DPUパフォーマンス設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)を参照してください。

   >[!NOTE]
   >
   >このファイルのAdobeを変更する前に、パラメーターにお問い合わせください。

   ![](assets/cfg_DPU_egvalues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、「**[!UICONTROL Save]**」をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]** / *&lt;**[!UICONTROL server name]***&#x200B;を選択します。
