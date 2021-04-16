---
description: 管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。
title: 管理アラートの設定
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# 管理アラートの設定{#configuring-administrative-alerts}

管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。

**推奨頻度：** 実稼働前

>[!NOTE]
>
>管理警告を使用するには、[!DNL Insight Server]が転送用SMTPサーバーにアクセスして、アラートを電子メールで送信する必要があります。

電子メール通知の受信者は、システム管理の主要担当者と主要な関係者である必要があります。

[!DNL Administrative Alerts.cfg]は、管理アラートファイルを使用して、[!DNL Insight Server]の管理アラートを構成します。

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスター[!DNL Insight Server]にアラートを作成または変更する必要があります。

**管理アラートを作成または変更するには**

1. [!DNL Insight]の「[!DNL Admin]/[!DNL Dataset and Profile]」タブで、**[!UICONTROL Servers Manager]**&#x200B;サムネールをクリックして、サーバーマネージャーワークスペースを開きます。
1. 設定する[!DNL Insight Server]のアイコンを右クリックし、「**[!UICONTROL Server Files]**」をクリックします。
1. [!DNL Server Files Manager]の&#x200B;**[!UICONTROL Components]**&#x200B;をクリックして、内容を表示します。 [!DNL Administrative Alerts.cfg] ファイルは、このディレクトリ内に格納されています。
1. [!DNL Administrative Alerts.cfg]の*server name *列のチェックマークを右クリックし、**[!UICONTROL Make Local]**&#x200B;をクリックします。 [!DNL Administrative Alerts.cfg]の[!DNL Temp]列にチェックマークが表示されます。
1. [!DNL Temp]列に新しく作成されたチェックマークを右クリックし、**[!UICONTROL Open]**/**[!UICONTROL in Insight]**&#x200B;をクリックします。
1. [!DNL Administrative Alerts.cfg]ウィンドウで、**[!UICONTROL component]**&#x200B;をクリックして内容を表示します。
1. 必要に応じてパラメーターを入力します。 このファイルで使用できるパラメーターのリストについては、[管理アラートの構成設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)を参照してください。

   ![ステップ情報](assets/cfg_adminalerts_examplevalues.png)

1. 次の操作を行って、変更をサーバーに保存します。

   1. ウィンドウ上部の&#x200B;**[!UICONTROL (modified)]**&#x200B;を右クリックし、**[!UICONTROL Save]**&#x200B;をクリックします。

   1. [!DNL Server Files Manager]で、[!DNL Temp]列のファイルのチェックマークを右クリックし、**[!UICONTROL Save to]**/***[!UICONTROL server name]***&#x200B;を選択します。

1. （オプション）クラスターで作業していて、同じ管理警告を各データ処理ユニットに適用する場合は、更新した[!DNL Administrative Alerts.cfg]ファイルをコピーして、マスター[!DNL Insight Server]インストールディレクトリ内の[!DNL Components for Processing Servers]フォルダーに貼り付ける必要があります。
