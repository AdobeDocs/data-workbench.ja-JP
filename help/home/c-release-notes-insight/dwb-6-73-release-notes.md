---
description: Data Workbench 6.73の新機能および修正点です。
title: Data Workbench 6.73 のリリースノート
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.73 のリリースノート{#data-workbench-release-notes}

Data Workbench 6.73の新機能および修正点です。

## Data Workbench 6.73 のリリースノート {#topic-7655534554ac4a4b816af1bd73b06aad56757}

Data Workbench 6.73の新機能および修正点です。

## 修正点 {#section-160baf6ea04c45a993777ee4260691ed}

* 一部の高解像度および高 DPI ハードウェアでユーザーがサインインできない問題を修正しました。
* IMSログインを使用すると、アーカイブファイル名に電子メールが含まれないというサーバーの問題を修正。
* OpenSSL を、いくつかの脆弱性の修正と新しい SSL 暗号化を含むバージョン 1.1.0h に更新しました。
* 以下のリストのオープンソースライブラリを最新の安定したバージョンに更新しました。

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Lookup ファイル行数がサポートされている 357913908 行を超えた場合のエラーログを追加しました。

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbenchワークステーションバージョン6.73は、Data Workbenchサーバーバージョン6.61以前のバージョンに接続しません。 その理由は、古いバージョンのサーバは、バージョン6.73ではサポートされていない暗号の弱い形式を使うからだ。古いバージョンのサポートを有効にするには

   1. OpenSSLバージョン1.0.1hでサポートされている強力な暗号リストを使用して、サーバ上のデフォルトのSSL暗号を上書きします。 上書きするには、「Components」ディレクトリと「Components for Processing Servers」ディレクトリにある「Communications.cfg」ファイルに鍵「SSL Ciphers」を追加します。 次に例を示します。`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >キーがSSLポートと同じレベルに配置されていることを確認します。 詳しくは、「通信設定」 [を参照してください。](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)

   1. 最新のtrust_ca_cert.pemファイルをサーバー6.61および古いサーバーに配置します。 この設定は、すべてのWorkstation 6.7xバージョンに適用されます。

Data Workbench 5.3 から 5.52 までについては、[アーカイブされているリリースノート](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)を参照してください。
