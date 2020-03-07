---
description: デジタル証明書に関する一般的な情報と、それらをダウンロードしてインストールする手順について説明します。
solution: Insight
title: デジタル証明書のダウンロードとインストール
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Downloading and Installing the Digital Certificates{#downloading-and-installing-the-digital-certificates}

デジタル証明書に関する一般的な情報と、それらをダウンロードしてインストールする手順について説明します。

* [デジタル証明書について](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [ノードロックされた証明書](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [最新の証明書](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [インターネットにアクセスできないコンピューターでのデジタル証明書の使用](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [デジタル証明書のインストール手順](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## デジタル証明書について {#section-e48a776ef39042759d1dfb3444996d8b}

アドビは、X.509 デジタル証明書を使用して実装されたクライアントおよびサーバーコンポーネントを識別し、認証します。

サーバーコンポーネント（または）をイン [!DNL Insight Server] ストールす [!DNL Repeater]る場合は、アドビがコンポーネント用に発行したデジタル証明書をインストールする必要があります。 アドビのアプリケーションを別のコンピューターに移行する必要がある場合は、アドビから新しい証明書を入手する必要があります。 その場合は、アドビカスタマーケアにお問い合わせください。

この証明書に表示される共通名は、指定したドメイン名(例： [!DNL vs001a.mycompany.com])でサーバーを識別します。 サーバークライアントがこのサーバーに接続すると、サーバーはこの証明書を、クライアントが要求したサーバーであることを証明する証明書として表示します。

Similarly, when you install a server client (for example, [!DNL Insight] or [!DNL Report]) you must install the digital certificate that authorizes a named individual (for example, Jane Smith) to use the installed client application. Adobeアプリケーションを別のコンピューターまたは別の名前付きユーザーに移行する必要がある場合は、アドビから新しい証明書を取得する必要があります。 その場合は、アドビカスタマーケアにお問い合わせください。

クライアントアプリケーションは、このデジタル証明書を提示して、サーバコンポーネントにアクセスします。 サーバーコンポーネントの管理者は、クライアントの証明書に表示される共通名または組織単位の値に基づいて、サーバーリソースへのアクセスを制限できます。

また、アドビアプリケーションと一緒にインストールされる X.509 デジタル証明書は、クライアントおよびサーバーコンポーネントが Secure Sockets Layer（SSL）経由で情報を交換する場合にも使用されます。SSL では、公開鍵と秘密鍵の暗号化システムを使用して HTTP 経由の送信のセキュリティを確保します。アドビの SSL 実装は、1024 ビットの RSA キーをサポートし、128 ビットの RC4 暗号化アルゴリズムを使用します。

セキュリティに加えて、インストールしたデジタル証明書は、インストール済みのアドビソフトウェアを実行するためのライセンスキーとしても機能します。 正常に機能させるには、デジタル証明書がノードロックされ、最新の状態である必要があります。そうでないと、アプリケーションが起動しません。

## 文字列の暗号化 {#section-8abe6b2d95704d38a04137d5c4602f0b}

パスワード [を暗号化するための文字列の暗号化](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) (String Encryption)を参照してください。

## ノードロックされた証明書 {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

ノードロックされた証明書とは、その証明書がインストールされているコンピューターに登録されたデジタル証明書です。 ノードロックは、証明書を特定のノード識別子（特定のマシンを一意に識別する値）に永続的に関連付けます。 証明書をノードロックするには、コンピューターがAdobe License ServerまたはLicense Serverにアクセスできるプロキシサーバーにインターネットでアクセスできる必要があります。

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

インターネットにアクセスできるコンピューターにをインストールする場合は、アドビ製品を初めて起動したときに、デジタル証明書が自動的にノードロックされます。 ノードロックされた後は、証明書を他のコンピューターで使用することはできません。 アドビ製品を別のコンピューターに移行する必要がある場合は、アドビから新しいロック解除済みの証明書を入手する必要があります。

## 最新の証明書 {#section-15aabaa8625c46edaa7436e1f3fc29c5}

ノードロックされている以外に、デジタル証明書は最新のものである必要があります。 最新の状態に維持するには、証明書を定期的に再検証する必要があります（通常は 30 日ごとですが、アドビとの契約によって異なります）。お使いのコンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。 アドビ製品は、必要に応じてLicense Serverに自動的に接続し、証明書を再検証します。 お使いのコンピューターにインターネットにアクセスできない場合は、次の節の説明に従って、更新された証明書を手動でインストールする必要があります。

## Using Digital Certificates on Machines Without Internet Access {#section-809366329a7d4e198f95fe06c1f534fa}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Insight Server]. 事前にロックされた証明書は、アドビがコンピューターのノード識別子に手動でロックするデジタル証明書です。

事前にロックされた証明書をリクエストするには、ノード識別子と証明書番号をアドビのカスタマーケアに送信する必要があります。 お使いのコンピューターのノードIDを取得するには、アドビカスタマーケアに問い合わせて、Adobe Node Identifierユーティリティをリクエストしてください。 また、アドビソフトウェアがLicense Serverへの接続を試行し、接続できない場合にアドビソフトウェアが発行するという警告からノード識別子を取得することもできます。

When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). 証明書を再検証する必要がある場合は、検証済みの新しい証明書をLicense Serverからダウンロードし、コンピューターに再インストールする必要があります。

## デジタル証明書のインストール手順 {#section-19f31676aad344a98e26e4fca1fad03b}

**デジタル証明書をダウンロードしてインストールするには**

1. Webブラウザーでhttps://aap.adobe.comを開 [きます](https://aap.adobe.com)。

   >[!NOTE]
   >
   >この時点で、ブラウザーからデジタル証明書の提示を求められる場合があります。 If it does, simply click **[!UICONTROL Cancel]** to dismiss the dialog box.

1. On the login screen, enter the **[!UICONTROL Account Name]** and the **[!UICONTROL Password]** that you received from Adobe, then click **[!UICONTROL login]**.

1. 自分用に発行された証明書を探し、その証 [!DNL Insight Server]明書に関連付けられたアイコンをクリックします。

   >[!NOTE]
   >
   >この証明書に割り当てられている共通名をメモしておきます。 この名前は後で使用します。

1. When prompted to save the certificate, click **[!UICONTROL Save]**. （ファイルの名前は、証明書に関連付けられている共通名と一致します）。
1. Download the file to the [!DNL Certificates] folder in the directory where you installed [!DNL Insight Server]. This folder already contains a certificate file named [!DNL trust_ca_cert.pem]. この証明書ファイルは常に存在する必要があります。

1. ダウンロードした証明書ファイルの名前を次に変更します。

[!DNL server_cert.pem]

