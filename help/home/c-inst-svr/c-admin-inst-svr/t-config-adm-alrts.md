---
description: 管理アラートは、通常の操作中に Insight サーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。
title: 管理アラートの設定
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 5%

---

# 管理アラートの設定{#configuring-administrative-alerts}

{{eol}}

管理アラートは、通常の操作中に Insight サーバーでエラーが検出された場合、指定した電子メールアドレスに電子メール通知を送信します。

**推奨頻度：** 実稼動前

>[!NOTE]
>
>管理アラートを使用するには、次の条件が必要です。 [!DNL Insight Server] は、メールでアラートを送信するために、転送 SMTP サーバーにアクセスできます。

電子メール通知の受信者は、主要なシステム管理担当者および主要な関係者である必要があります。

管理アラートファイル [!DNL Administrative Alerts.cfg]：の管理アラートを設定するために使用します。 [!DNL Insight Server].

>[!NOTE]
>
>クラスタを実行している場合は、マスター上でアラートを作成または変更する必要があります [!DNL Insight Server] クラスター内で使用します。

**管理アラートを作成または変更するには**

1. In [!DNL Insight]、 [!DNL Admin] > [!DNL Dataset and Profile] タブで、 **[!UICONTROL Servers Manager]** サムネールを使用して、サーバーマネージャーワークスペースを開きます。
1. 次のアイコンを右クリック： [!DNL Insight Server] を設定して、 **[!UICONTROL Server Files]**.
1. 内 [!DNL Server Files Manager]をクリックし、 **[!UICONTROL Components]** をクリックして、その内容を表示します。 [!DNL Administrative Alerts.cfg] ファイルは、このディレクトリ内に格納されています。
1. 以下の「サーバー名」列のチェックマークを右クリックします。 [!DNL Administrative Alerts.cfg] をクリックし、 **[!UICONTROL Make Local]**. チェックマークが [!DNL Temp] 列 [!DNL Administrative Alerts.cfg].
1. 新しく作成された、 [!DNL Temp] 列とクリック **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 内 [!DNL Administrative Alerts.cfg] ウィンドウ、クリック **[!UICONTROL component]** をクリックして、その内容を表示します。
1. 必要に応じてパラメーターを入力します。 このファイルで使用できるパラメーターの一覧については、 [管理アラートの構成設定](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![ステップ情報](assets/cfg_adminalerts_examplevalues.png)

1. 次の手順を実行して、変更をサーバーに保存します。

   1. 右クリック **[!UICONTROL (modified)]** ウィンドウの上部にあるをクリックし、 **[!UICONTROL Save]**.

   1. 内 [!DNL Server Files Manager]をクリックし、 [!DNL Temp] 列と選択 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. （オプション）クラスター内で作業していて、各データ処理ユニットに同じ管理アラートを適用する場合は、更新した [!DNL Administrative Alerts.cfg] ファイルを [!DNL Components for Processing Servers] マスター内のフォルダー [!DNL Insight Server] インストールディレクトリ。
