---
description: 電子証明書をダウンロードしてインストールする手順です。
title: 電子証明書のインストール手順
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 42%

---

# 電子証明書のインストール手順{#digital-certificate-installation-procedures}

{{eol}}

電子証明書をダウンロードしてインストールする手順です。

1. Web ブラウザーを開き、[https://aap.adobe.com](https://aap.adobe.com) へ移動します。

   >[!NOTE]
   >
   >この時点で、ブラウザーから電子証明書を提示するように求められる場合があります。該当する場合は、 **[!UICONTROL Cancel]** をクリックして、ダイアログボックスを閉じます。

1. ログイン画面で、「アカウント名」と「Adobe」から受け取ったパスワードを入力し、「 **[!UICONTROL login]**.
1. のインスタンス用に発行された証明書を見つけます。 [!DNL Report] サーバー (*名前*.pem) をクリックし、 ![](assets/btn_save_certificatedownload.PNG) その証明書に関連付けられているアイコン。
1. 証明書を保存するように求められた場合は、「**[!UICONTROL Save]**」をクリックします。
1. [!DNL Report Server] をインストールしたディレクトリ内の Certificates フォルダーにファイルをダウンロードします。

   このフォルダーには、[!DNL trust_ca_cert.pem] という名前の証明書ファイルが既に含まれています。両方の証明書ファイルが常に存在する必要があるのは、次の場合です。 [!DNL Report] サーバーが機能する。
