---
description: Windows 証明書ストアを使用すると、サーバーとの SSL 通信のために、クライアントの証明書と秘密鍵を Windows 証明書ストアに格納できます。
title: Windows 証明書ストア
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: ht
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: ht
source-wordcount: '1000'
ht-degree: 100%

---


# Windows 証明書ストア {#windows-certificate-store}

Windows 証明書ストアを使用すると、サーバーとの SSL 通信のために、クライアントの証明書と秘密鍵を Windows 証明書ストアに格納できます。

クライアント向けの Windows 証明書ストアは新しい機能で、SSL 通信証明書および秘密鍵を、`Insight/Certificates/<CertName>.pem` ファイルではなく、Windows 証明書ストアに格納できます。Windows 証明書ストアの使用は、他のアプリケーションに証明書ストアを使用する場合、および 1 か所で証明書管理を行いたい場合に適しています。また、Windows 証明書ストアが提供するその他の Windows 監査ログを使用したいユーザーに適しています。

>[!NOTE]
>
>ライセンスサーバーを使用したライセンスは、既存の `<Common Name>.pem` ファイルを使用して管理されており、証明書ストアから取得した証明書は、指定したサーバーとの通信にのみ使用されます。

## 前提条件 {#section-69b18600052145ff8e5299b7123e69c5}

1. [!DNL certmgr.msc] ファイルへのアクセス権を持っていて、証明書と鍵を **Personal** ストアにインポートできる必要があります。（これは、デフォルトではほとんどの Windows ユーザーに当てはまります。）

1. 設定を行うユーザーは、**OpenSSL** コマンドラインツールのコピーを持っている必要があります。
1. サーバーおよびクライアントは、[カスタム証明書の使用](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)（**Certificates** ディレクトリではなく、Windows 証明書ストアにクライアント証明書を格納するための手順が記されています）で説明されているとおりに、既にカスタム SSL 証明書を使用するように設定されている必要があります。

## Windows 証明書ストアの設定 {#section-3629802122e947d4b4f63e8b732cfe27}

クライアント向けの Windows 証明書ストアは、次の手順で有効になります。

**手順 1：ユーザーの SSL 証明書および秘密鍵を Windows 証明書ストアに読み込む。**

 [カスタム証明書の使用](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd)で、SSL 証明書および鍵を次のディレクトリに配置するように指示されます。

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

証明書の名前は `<Common Name>.pem`（[!DNL Analytics Server 1.pem] など）になります（[!DNL trust_ca_cert.pem] ファイルではありません）。

証明書と秘密鍵が読み込めるようになる前に、.[!DNL pem] 形式から [!DNL .pfx] 形式（[!DNL pkcs12.pfx] など）に変換しておく必要があります）。

1. コマンドプロンプトまたはターミナルを開き、次のディレクトリに移動します。

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. 次の引数（および実際の [!DNL openssl] ファイル名）で [!DNL .pem] を実行します。

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   書き出しパスワードを求めるメッセージが表示されたら、**Enter** キーを押して入力をスキップします。

1. ファイル名を指定して実行、スタートメニューまたはコマンドラインから [!DNL certmgr.msc] を実行します。
1. 現在のユーザーの&#x200B;**個人**&#x200B;証明書ストアを開きます。

   ![](assets/6_5_crypto_api_0.png)

1. **証明書**&#x200B;を右クリックして、**すべてのタスク**／**インポート**&#x200B;をクリックします。

   「**現在のユーザー**」オプションが選択されていることを確認して、「**次へ**」をクリックします。

   ![](assets/6_5_crypto_api_4.png)

1. 「**参照**」をクリックし、以前作成した `<CommonName>.pfx` ファイルを選択します。ファイル拡張子ドロップダウンボックスを X.509 証明書から **Personal Information Exchange** または&#x200B;**すべてのファイル**&#x200B;のどちらかに変更する必要があります。

   ファイルを選択して、「**開く**」をクリックし、「**次へ**」をクリックします。

1. パスワードは入力せず、「**このキーをエクスポート可能にする**」および「**すべての拡張プロパティを含める**」オプションのみが選択されていることを確認します。

   ![](assets/6_5_crypto_api_3.png)

   「**次へ**」をクリックします。

1. 「**証明書をすべて次のストアに配置する**」が選択されていることと証明書ストアが「**個人**」にリストされていることを確認します。（上級ユーザーの場合、この時点で別のストアを選択できますが、後で設定を変更する必要があります。）

1. **「次へ」**&#x200B;をクリックし、**「完了」**&#x200B;をクリックします。インポートが成功したことを示すダイアログボックスが表示されると、ストアの証明書フォルダーに証明書が表示されます。

   >[!NOTE]
   >
   >「**発行先**」および「**発行者**」フィールドには特に注意を払います。これらは、次の手順で必要になります。

**手順 2：Insight.cfg ファイルを編集する。**

[!DNL Insight.cfg] ファイルは、Data Workbench に Windows 証明書ストア機能を使用することを指示するために、編集する必要があります。このファイルの各サーバーエントリには、いくつかの追加のパラメーターが指定されている必要があります。パラメーターが省略されると、ワークステーションは既存の証明書設定を使用するデフォルト設定になります。パラメーターが指定されているが誤った値の場合、ワークステーションはエラー状態を入力し、ユーザーはエラー情報についてログファイルを参照する必要があります。

1. **Insight.cfg** ファイルを開きます（**Insight** インストールディレクトリにあります）。

1. 設定したいサーバーエントリまでスクロールします。すべてのサーバーで Windows 証明書ストアを使用したい場合、[!DNL serverInfo] オブジェクトのベクトルにあるすべてのエントリに対して、これらの修正を行う必要があります。
1. [!DNL Insight.cfg] ファイル内に、次のパラメーターを追加します。この作業は、ワークステーションから実行するか、これらのパラメーターを手動で [!DNL serverInfo] オブジェクトに追加することで実行できます（このファイルでは、タブ文字ではなく必ず通常のスペースを使用してください。また、スペルや文法の間違いがないように注意してください）。

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   bool 型のパラメーターは、この機能を有効または無効に設定するものです。証明書名は、証明書マネージャーの「**発行先**」に一致します。証明書の発行者名は、「**発行者**」に一致し、「**ストア名**」は、証明書ストア名に一致する必要があります。

   >[!NOTE]
   >
   >証明書マネージャー（certmgr.msc）の「個人」という名前は、実際は「My」という名前の証明書ストアを参照しています&#x200B;**。**&#x200B;その結果、推奨のとおりに SSL 通信証明書および鍵（.PFX）を「**個人**」証明書ストアにインポートする場合、**SSL CryptoAPI Cert Store Name** 文字列を &quot;My&quot; に設定する必要があります。このパラメーターを &quot;Personal&quot; に設定すると、機能しなくなります。これは、Windows 証明書ストアに独特のものです。

   事前定義されたシステムストアの完全なリストについては、次の場所から入手できます：[https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx)。お使いのシステムには、その他の証明書ストアがある場合があります。「個人」（**My** など）以外のストアを使用したい場合、証明書ストアの正規名を入手し、[!DNL Insight.cfg] ファイルに指定する必要があります。（システムストア名「My」は、Windows ドキュメントでは、「My」および「MY」と一貫性なく呼ばれています。このパラメーターは、大文字と小文字が区別されないようです。）

1. これらのパラメーターを追加して、値が Windows 証明書マネージャーのリストと一致するのを検証したら、[!DNL Insight.cfg] ファイルを保存します。

これで、ワークステーションを開始（またはサーバーから切断／再接続）できます。Data Workbench は、証明書ストアから証明書および秘密鍵を読み込んで、通常どおりに接続します。

## ログ出力 {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

証明書が見つからない場合や有効でない場合は、[!DNL HTTP.log] ファイルに次のエラーメッセージが記録されます。

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>L4 ログフレームワークを有効にするには、[!DNL L4.cfg] ファイルをセットアップします（セットアップ方法についてはアカウントマネージャーにお問い合わせください）。
