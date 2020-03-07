---
description: Communications設定ファイルCommunications.cfgには、Insight Serverのネットワーク設定と、Access Control.cfgファイルへのパスが含まれます。
solution: Insight
title: 通信の設定
uuid: 04d08206-17b1-4348-a945-0c907c9a494c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 通信の設定{#configuring-communications}

Communications設定ファイルCommunications.cfgには、Insight Serverのネットワーク設定と、Access Control.cfgファイルへのパスが含まれます。

これらの設定は、に接続する際に役立ちま [!DNL Insight Server]す。

**推奨頻度：** 必要な場合のみ

**通信の設定を表示および変更するには[!DNL Insight]**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Communications.cfg] ファイルは、このディレクトリ内に格納されています。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Communications.cfg] window, click **[!UICONTROL component]** to view its contents.
1. 必要に応じて設定を変更します。 このファイルで使用できるパラメータの詳細については、「通信の構成 [設定」を参照してくださ](../../../home/c-inst-svr/c-cfg-stgs-ref/c-comm-cfg-stgs.md#concept-aed00587c7a1432fb487bd154aaea6b1)い。

   ![ステップ情報](assets/cfg_communications_examplevalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

