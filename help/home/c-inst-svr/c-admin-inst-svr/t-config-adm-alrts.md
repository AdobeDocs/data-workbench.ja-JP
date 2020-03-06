---
description: 管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。
solution: Insight
title: 管理アラートの設定
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 管理アラートの設定{#configuring-administrative-alerts}

管理アラートは、通常の操作中にInsightサーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。

**推奨頻度：** 実稼働前

>[!NOTE]
>
>管理アラートを使用するには、転送中のSMTPサ [!DNL Insight Server] ーバーにアクセスして、アラートを電子メールで送信する必要があります。

電子メール通知の受信者は、システム管理の主要担当者と主な関係者である必要があります。

管理アラートファイルは、 [!DNL Administrative Alerts.cfg]の管理アラートの設定に使用されま [!DNL Insight Server]す。

>[!NOTE]
>
>クラスターを実行している場合は、クラスター内のマスターに対してアラートを作成または変 [!DNL Insight Server] 更する必要があります。

**管理アラートを作成または変更するには**

1. の「/」 [!DNL Insight]タブで、サ [!DNL Admin] ムネールを [!DNL Dataset and Profile] クリックして、サーバ **[!UICONTROL Servers Manager]** ーマネージャーワークスペースを開きます。
1. 設定するのアイコンを右ク [!DNL Insight Server] リックし、をクリックします **[!UICONTROL Server Files]**。
1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. [!DNL Administrative Alerts.cfg] ファイルは、このディレクトリ内に格納されています。
1. の*server name *列のチェックマークを右クリックし、をクリ [!DNL Administrative Alerts.cfg] ックしま **[!UICONTROL Make Local]**&#x200B;す。 A check mark appears in the [!DNL Temp] column for [!DNL Administrative Alerts.cfg].
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In the [!DNL Administrative Alerts.cfg] window, click **[!UICONTROL component]** to view its contents.
1. 必要に応じてパラメータを入力します。 このファイルで使用できるパラメータの一覧については、「管理アラートの設定」 [を参照してくださ](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)い。

   ![ステップ情報](assets/cfg_adminalerts_examplevalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. ウィンドウ上部 **[!UICONTROL (modified)]** のを右クリックし、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   1. で、列 [!DNL Server Files Manager]内のファイルのチェックマークを右クリックし [!DNL Temp] て、/ **[!UICONTROL Save to]** &lt; ***[!UICONTROL server name]**>を選択します*。

1. （オプション）クラスター内で作業していて、同じ管理警告を各データ処理ユニットに適用する場合は、更新したファイルをコピーして、マスターインストールディレクトリ内のフォルダーに貼り付 [!DNL Administrative Alerts.cfg] ける必要が [!DNL Components for Processing Servers][!DNL Insight Server] あります。
