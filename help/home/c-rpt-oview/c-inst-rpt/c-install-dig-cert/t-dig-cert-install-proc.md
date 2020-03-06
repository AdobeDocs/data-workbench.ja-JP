---
description: デジタル証明書をダウンロードしてインストールする手順です。
solution: Analytics
title: デジタル証明書のインストール手順
topic: Data workbench
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# デジタル証明書のインストール手順{#digital-certificate-installation-procedures}

デジタル証明書をダウンロードしてインストールする手順です。

1. Webブラウザーでhttps://aap.adobe.comを開 [きます](https://aap.adobe.com)。

   >[!NOTE]
   >
   >この時点で、ブラウザーからデジタル証明書の提示を求められる場合があります。 If it does, just click **[!UICONTROL Cancel]** to dismiss the dialog box.

1. On the login screen, enter the Account Name and the Password that you received from Adobe, then click **[!UICONTROL login]**.
1. Locate the certificate that has been issued for your instance of [!DNL Report] Server (*Your Name*.pem) and click the ![](assets/btn_save_certificatedownload.PNG) icon associated with that certificate.
1. When prompted to save the certificate, click **[!UICONTROL Save]**.
1. [!DNL Report Server] をインストールしたディレクトリ内の Certificates フォルダーにファイルをダウンロードします。

   This folder already contains a certificate file named [!DNL trust_ca_cert.pem]. Both certificate files must always be present for [!DNL Report] Server to function.

