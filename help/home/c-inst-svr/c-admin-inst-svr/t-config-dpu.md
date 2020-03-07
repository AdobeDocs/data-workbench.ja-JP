---
description: DPU設定ファイルDPU.cfgは、Insightサーバーの様々なパフォーマンスパラメーターを指定します。
solution: Insight
title: DPU.cfgの設定
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DPU.cfgの設定{#configuring-dpu-cfg}

DPU設定ファイルDPU.cfgは、Insightサーバーの様々なパフォーマンスパラメーターを指定します。

これらのパラメーターの設定方法は、データセットのサイズやその他多くの要因によって異なります。 パフォーマンス調整に関するヘルプについては、アドビのコンサルティングサービスにお問い合わせください。

**推奨頻度：** 必要な場合のみ

**DPUパフォーマンス[!DNL Insight Server]設定を変更するには**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL DPU.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL DPU.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL DPU.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL DPU.cfg] window, click component to view its contents.
1. 必要に応じて、パフォーマンスとパスの設定を変更します。 このファイルで使用できるパラメーターの一覧については、 [DPUパフォーマンス設定を参照してください](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1)。

   >[!NOTE]
   >
   >このファイルのパラメーターを変更する前に、アドビにお問い合わせください。

   ![](assets/cfg_DPU_egvalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

