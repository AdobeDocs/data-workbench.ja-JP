---
description: Communications設定ファイルCommunications.cfgには、Insight Serverのネットワーク設定と、アクセス制御.cfgファイルへのパスが含まれています。
title: 通信の設定
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
exl-id: af5e788e-8904-4c68-b02a-c95b523b076d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# 通信の設定{#configuring-communications}

Communications設定ファイルCommunications.cfgには、Insight Serverのネットワーク設定と、アクセス制御.cfgファイルへのパスが含まれています。

これらの設定は、[!DNL Insight Server]に接続する際に役立ちます。

**推奨頻度：** 必要な場合のみ

**通信設定を表示および変更するには[!DNL Insight]**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components]**&#x200B;をクリックして、内容を表示します。 [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. [!DNL Communications.cfg]の&#x200B;*サーバー名*&#x200B;列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Communications.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL Communications.cfg]ウィンドウで、**[!UICONTROL component]**&#x200B;をクリックして内容を表示します。
1. 必要に応じて設定を変更します。 このファイルで使用できるパラメーターについて詳しくは、[通信構成設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)を参照してください。

   ![ステップ情報](assets/cfg_communications_examplevalues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;を選択します。
