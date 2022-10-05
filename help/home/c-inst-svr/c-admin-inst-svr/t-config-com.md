---
description: Communications 設定ファイル Communications.cfg には、Insight Server のネットワーク設定と、Access Control.cfg ファイルへのパスが含まれています。
title: 通信の設定
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# 通信の設定{#configuring-communications}

{{eol}}

Communications 設定ファイル Communications.cfg には、Insight Server のネットワーク設定と、Access Control.cfg ファイルへのパスが含まれています。

これらの設定は、 [!DNL Insight Server].

**推奨頻度：** 必要な場合のみ

**で通信設定を表示および変更するには[!DNL Insight]**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. チェックマーク ( *サーバー名* 列 [!DNL Communications.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Communications.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 内 [!DNL Communications.cfg] ウィンドウ、クリック **[!UICONTROL component]** をクリックして、その内容を表示します。
1. 必要に応じて設定を変更します。 このファイルで使用できるパラメーターについて詳しくは、 [通信の構成設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1).

   ![ステップ情報](assets/cfg_communications_examplevalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
