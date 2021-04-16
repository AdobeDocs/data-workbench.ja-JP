---
description: デジタル証明書をダウンロードしてインストールする手順です。
title: 電子証明書のインストール手順
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 42%

---

# 電子証明書のインストール手順{#digital-certificate-installation-procedures}

デジタル証明書をダウンロードしてインストールする手順です。

1. Web ブラウザーを開き、[https://aap.adobe.com](https://aap.adobe.com) へ移動します。

   >[!NOTE]
   >
   >この時点で、ブラウザーから電子証明書を提示するように求められる場合があります。表示されている場合は、**[!UICONTROL Cancel]**&#x200B;をクリックしてダイアログボックスを閉じます。

1. ログイン画面で、Adobeから受け取ったアカウント名とパスワードを入力し、**[!UICONTROL login]**&#x200B;をクリックします。
1. [!DNL Report]サーバーのインスタンスに対して発行された証明書を探し（*お客様の名前*.pem）、その証明書に関連付けられた![](assets/btn_save_certificatedownload.PNG)アイコンをクリックします。
1. 証明書を保存するように求められた場合は、「**[!UICONTROL Save]**」をクリックします。
1. [!DNL Report Server] をインストールしたディレクトリ内の Certificates フォルダーにファイルをダウンロードします。

   このフォルダーには、[!DNL trust_ca_cert.pem] という名前の証明書ファイルが既に含まれています。[!DNL Report]サーバーが機能するには、両方の証明書ファイルが常に存在する必要があります。
