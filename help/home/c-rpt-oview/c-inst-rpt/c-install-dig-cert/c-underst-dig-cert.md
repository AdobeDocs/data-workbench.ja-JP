---
description: アドビは、X.509 デジタル証明書を使用して実装されたクライアントおよびサーバーコンポーネントを識別し、認証します。
solution: Analytics
title: デジタル証明書について
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# デジタル証明書について{#understanding-digital-certificates}

アドビは、X.509 デジタル証明書を使用して実装されたクライアントおよびサーバーコンポーネントを識別し、認証します。

[!DNL Report Server] をインストールする場合は、インストールしたクライアントアプリケーションを使用するために、指定された個人（例えば、Jane Smith）を認証するデジタル証明書をインストールする必要があります。

>[!NOTE]
>
>If you need to migrate [!DNL Report Server] to another machine or another named user, you must obtain a new certificate from Adobe. その場合は、アドビカスタマーケアにお問い合わせください。

[!DNL Report Server] は、サーバーコンポーネントへのアクセス権を取得するために、このデジタル証明書を利用します。サーバーコンポーネントの管理者は、クライアントの証明書に表示される共通名または組織単位の値に基づいて、サーバーリソースへのアクセスを制限できます。

また、アドビアプリケーションと一緒にインストールされる X.509 デジタル証明書は、クライアントおよびサーバーコンポーネントが Secure Sockets Layer（SSL）経由で情報を交換する場合にも使用されます。SSL では、公開鍵と秘密鍵の暗号化システムを使用して HTTP 経由の送信のセキュリティを確保します。アドビの SSL 実装は、1024 ビットの RSA キーをサポートし、128 ビットの RC4 暗号化アルゴリズムを使用します。

In addition to security, the digital certificate that you install also functions as a license key that enables you to run the installed [!DNL Report Server]. 正常に機能させるには、ノードロックされた最新のデジタル証明書が必要です。これがないと、アプリケーションは起動しません。

## ノードロックされた証明書 {#section-3338f1558e7844888dced8f395888744}

ノードロックされた証明書とは、その証明書がインストールされているコンピューターに登録されたデジタル証明書です。 ノードロックは、証明書を特定のノード識別子（特定のマシンを一意に識別する値）に永続的に関連付けます。 証明書をノードロックするには、コンピューターがAdobe License ServerまたはLicense Serverにアクセスできるプロキシサーバーにインターネットでアクセスできる必要があります。

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) on this page.

If you are installing on a machine that can access the Internet, your digital certificate is node-locked automatically the first time that you start [!DNL Report Server]. ノードロックされた後は、証明書を他のコンピューターで使用することはできません。 If you need to migrate [!DNL Report Server] to another machine, you must obtain a new, unlocked certificate from Adobe.

## 最新の証明書 {#section-b4053ab714514dfb97ea7f61bbb8da1e}

ノードロックされている以外に、デジタル証明書は最新のものである必要があります。 最新の状態を維持するには、証明書を定期的に再検証する必要があります（通常は30日ごとですが、アドビとの契約によって異なります）。 お使いのコンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。 必要に応じて、[!DNL Report Server] が License Server に自動的に接続し、証明書を再検証します。お使いのコンピューターにインターネットにアクセスできない場合は、次の節の説明に従って、更新された証明書を手動でインストールする必要があります。

## Using Digital Certificates on Machines Without Internet Access {#section-18cce05e2204407bb2b6b75deab9197d}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Report Server]. 事前にロックされた証明書は、アドビがコンピューターのノード識別子に手動でロックするデジタル証明書です。

事前にロックされた証明書をリクエストするには、ノード識別子と証明書番号をアドビのカスタマーケアに送信する必要があります。 To obtain the node identifier for your machine, contact Adobe Customer Care to request the Adobe [!DNL Node Identifier] utility. また、[!DNL Report Server] が License Server へのアクセスを試行して失敗した場合に発行されるアラートからノード識別子を入手することもできます。When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

証明書を再検証する必要がある場合は、検証済みの新しい証明書をLicense Serverからダウンロードし、コンピューターに再インストールする必要があります（アドビとの契約で別段の指定がない場合）。
