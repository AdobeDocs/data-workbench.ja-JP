---
description: カスタム証明書の使用に関する手順です。
title: Data Workbench でのカスタム証明書の使用
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 93%

---

# Data Workbench でのカスタム証明書の使用{#using-custom-certificates-in-data-workbench}

{{eol}}

カスタム証明書の使用に関する手順です。

Data Workbench クライアントまたはサーバーで使用される証明書は、信頼できる CA（証明機関）によって署名されている必要があります。Data Workbench のお客様は、Visual Sciences CA によって署名された証明書を受け取ります。[!DNL trust_ca_cert.pem]（Insight ソフトウェアと共に提供され、サーバーおよびクライアントの **Certificates** ディレクトリに格納されている）に Visual Sciences CA のルート CA 証明書&#x200B;**&#x200B;があるので、これらの証明書は、Data Workbench ソフトウェアによって信頼されます。これらの証明書は、クライアントとサーバーが SSL を使用してお互いに通信する場合に、ソフトウェアのライセンシングおよび認証に使用されます。Visual Sciences CA によって発行された証明書のみライセンシングに使用できますが、通信および認証にはその他の証明書が使用されることもあります。Visual Sciences 以外の CA によって発行された証明書は、「カスタム証明書&#x200B;**」と呼びます。

**重要なお知らせ：**&#x200B;サーバーおよびクライアントについて、Data Workbench ソフトウェアは、クライアントおよびサーバーの **Certificates** ディレクトリにインストールされた証明書ファイルまたは設定で明示的に識別された証明書を使用します。ただし、クライアントの場合、[Windows 証明書ストア](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d)を使用することもできます。

次に、Data Workbench クライアントおよびサーバーで通信するためにカスタム証明書を使用するための手順について説明します。すべてに厳密に従う必要があるわけではなく、プロセスでは様々なバリエーションが使用されます。ただし、以下の手順が機能することはテストされています。

## カスタムクライアント証明書の設定 {#section-2083fd41973e451fa404e7a4ae4da591}

1. 証明書を発行する CA を [!DNL trust_cert_ca.pem] に追加します。これは、クライアントおよびこのカスタム証明書を使用してアクセスできるすべてのクラスターのすべてのサーバーの **Certificates** ディレクトリにインストールされています。

1. 次の状態にあるクラスターの各サーバーのカスタム証明書を入手します。

   1. 証明書は [!DNL .pem] 証明書。
   1. 証明書は、その鍵を含んでおり、暗号化されていない（つまり、パスワード／パスフレーズがない）。

      証明書は、次の行のどちらかを持つ、その証明書の鍵を含んでいる。

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      パスワードフレーズを [!DNL .pem] 証明書：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 証明書に、CN、O、OU など（サーバーの [!DNL Access Control.cfg] ファイルでこのクライアントに必要とされている）がある。
   1. 証明書は *目的&#42;&#42;&#42;* / *client* ( または *server* **および** *client*) をクリックします。

      証明書がサーバーおよび／またはクライアントの purpose コードを持っていることを検証するには、次のコマンドを使用できます。

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      サーバー証明書の場合、両方のコマンドで次の結果が返されます。

      ```
      custom_communications_cert.pem: OK
      ```

      クライアント証明書の場合、[!DNL OK] が返されるには、2 番目のコマンドが必要です。

1. クライアントの **Certificates** ディレクトリに証明書を配置します。
1. [!DNL Insight.cfg] で、この証明書を使用する各クラスターの *serverInfo* の下に、*custom client cert* が指定されていることを確認します。例：

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## カスタムサーバー証明書の設定 {#setting-up-custom-server-certificates}

この節では、Visual Sciences が発行した証明書を使用した、稼動中のクラスターがあり、設定は一般的な慣習（例えば、マスターの *Components for Processing Servers* ディレクトリは、すべての DPU の *Components* ディレクトリと同期するなど）に従っていると仮定します。

1. 証明書を発行する CA を、クラスターのすべてのサーバーおよびこのクラスターと通信する必要のあるすべてのクライアントにインストールされた [!DNL trust_cert_ca.pem] に追加します。
1. 次の要件に沿ったクラスターの各サーバーのカスタム証明書を入手します。

   1. カスタム証明書は [!DNL .pem] 証明書。
   1. 証明書は、その鍵を含んでおり、暗号化されていない（つまり、パスワード／パスフレーズがない）。

      証明書は、その証明書の鍵（次のような行を持つ場合）を含んでいる。

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      パスワードフレーズを [!DNL .pem] 証明書：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 証明書は、現在サーバーにインストールされている [!DNL server_cert.pem] と同じ CN を持っている。
   1. 証明書は、*server* および&#x200B;*client* の purpose を使用して発行された。

      証明書がサーバーおよび／またはクライアントの purpose コードを持っていることを検証するには、次のコマンドを使用できます。

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      サーバー証明書の場合、両方のコマンドで次の結果が返されます。

      ```
      custom_communications_cert.pem: OK
      ```

      クライアント証明書の場合、[!DNL OK] が返されるには、2 番目のコマンドが必要です。

1. 各サーバーのカスタム証明書を **としてサーバーの** Certificates[!DNL custom_communications_cert.pem] ディレクトリにインストールします。

1. テキストエディターを使用して、**Components** および *Components for Processing Servers* ディレクトリにある *Communications.cfg* ファイルの最初の行（[!DNL component = CommServer]）の直下に、次の行を追加します。

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. すべてのサーバーを再起動します。

**証明書の失敗の警告について**

Insight サーバーまたはクライアントが&#x200B;**ライセンス**&#x200B;証明書を **Certificates** ディレクトリに探す際に、Insight CA 証明書のハードコードされたコピーと対照して、すべての証明書（[!DNL trust_ca_cert.pem] を除く）を検証しようとします。これにより、このディレクトリに存在するすべてのカスタム証明書がエラーになります。サーバーは、次の警告を発します。

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

この警告は、無視してかまいません。
