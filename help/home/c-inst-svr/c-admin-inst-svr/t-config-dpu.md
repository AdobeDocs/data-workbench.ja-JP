---
description: DPU 設定ファイル DPU.cfg は、Insight サーバーの様々なパフォーマンスパラメーターを指定します。
title: DPU.cfg の設定
uuid: c348622b-7d4b-4cfa-a8f8-a07d91e440d5
exl-id: 55e4ea7f-fee3-4af7-9cbc-d121e79e6ab2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# DPU.cfg の設定{#configuring-dpu-cfg}

{{eol}}

DPU 設定ファイル DPU.cfg は、Insight サーバーの様々なパフォーマンスパラメーターを指定します。

これらのパラメーターの設定方法は、データセットのサイズやその他の様々な要因によって異なります。 パフォーマンスの調整については、Adobeのコンサルティングサービスにお問い合わせください。

**推奨頻度：** 必要な場合のみ

**変更するには [!DNL Insight Server] DPU パフォーマンス設定**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL DPU.cfg] ファイルは、このディレクトリ内に格納されています。
1. チェックマーク ( *サーバー名* 列 [!DNL DPU.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL DPU.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 内 [!DNL DPU.cfg] ウィンドウで、「コンポーネント」をクリックして、コンテンツを表示します。
1. 必要に応じて、パフォーマンスとパスの設定を変更します。 このファイルで使用できるパラメーターの一覧については、 [DPU パフォーマンス設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-dpu-perf-stgs.md#concept-477c4c526de44bda84176e62266c3df1).

   >[!NOTE]
   >
   >このファイルのAdobeを変更する前に、パラメータに連絡してください。

   ![](assets/cfg_DPU_egvalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
