---
description: 管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。
solution: Analytics
title: 管理アラートの設定
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---


# 管理アラートの設定{#configuring-administrative-alerts}

管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。

**推奨頻度：** 実稼働前

>[!NOTE]
>
>管理警告を使用するには、転送中のSMTPサーバーにアクセス [!DNL Insight Server] して、通知を電子メールで送信する必要があります。

電子メール通知の受信者は、システム管理の主要担当者と主要な関係者である必要があります。

管理アラートファイル [!DNL Administrative Alerts.cfg]は、の管理アラートの設定に使用され [!DNL Insight Server]ます。

>[!NOTE]
>
>クラスタを実行している場合は、クラスタ内のマスタ上にアラートを作成または変更する必要 [!DNL Insight Server] があります。

**管理アラートを作成または変更するには**

1. の「>」 [!DNL Insight]タブで [!DNL Admin] 、 [!DNL Dataset and Profile]**[!UICONTROL Servers Manager]** サムネールをクリックしてサーバーマネージャーワークスペースを開きます。
1. 設定するアイコンを右クリック [!DNL Insight Server] し、をクリックし **[!UICONTROL Server Files]**&#x200B;ます。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Administrative Alerts.cfg] ファイルは、このディレクトリ内に格納されています。
1. の*server name *列のチェックマークを右クリックし、 [!DNL Administrative Alerts.cfg] をクリックし **[!UICONTROL Make Local]**&#x200B;ます。 A check mark appears in the [!DNL Temp] column for [!DNL Administrative Alerts.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Administrative Alerts.cfg] window, click **[!UICONTROL component]** to view its contents.
1. 必要に応じてパラメーターを入力します。 このファイルで使用できるパラメータのリストについては、「 [管理アラートの設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)」を参照してください。

   ![ステップ情報](assets/cfg_adminalerts_examplevalues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** を右クリックし、をクリックし **[!UICONTROL Save]**&#x200B;ます。

   1. で、列内 [!DNL Server Files Manager]のファイルのチェックマークを右クリックし、 [!DNL Temp] / **[!UICONTROL Save to]** &lt; *>を選択します&#x200B;**[!UICONTROL server name]***。

1. （オプション）クラスターで作業していて、各データ処理ユニットに同じ管理警告を適用する場合は、更新した [!DNL Administrative Alerts.cfg] ファイルをコピーして、マスター [!DNL Components for Processing Servers] インストールディレクトリ内の [!DNL Insight Server] フォルダーに貼り付ける必要があります。
