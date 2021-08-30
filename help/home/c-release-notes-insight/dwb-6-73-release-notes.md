---
description: Data Workbench6.73の新機能および修正点です。
title: Data Workbench 6.73 のリリースノート
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
exl-id: 911c0cb7-ad95-4dbb-90ff-8e5c40b19f7f
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 30%

---

# Data Workbench 6.73 のリリースノート{#data-workbench-release-notes}

Data Workbench6.73の新機能および修正点です。

## 修正点 {#section-160baf6ea04c45a993777ee4260691ed}

* 一部の高解像度および高 DPI ハードウェアでユーザーがサインインできない問題を修正しました。
* IMSログインを使用する際に、アーカイブファイル名に電子メールが表示されない問題を修正しました。
* OpenSSL を、いくつかの脆弱性の修正と新しい SSL 暗号化を含むバージョン 1.1.0h に更新しました。
* 以下に示すオープンソースライブラリを最新の安定したバージョンに更新しました

   * libssh2 1.8.0
   * Apache Xerces 3.2.1
   * Apache Xalan 1.11
   * libpng 1.6.34
   * libarchive 3.3.2
   * zlib 1.2.11
   * pcre 8.42

* Lookup ファイル行数がサポートされている 357913908 行を超えた場合のエラーログを追加しました。

## 既知の問題 {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbenchワークステーションのバージョン6.73は、Data Workbenchサーバーのバージョン6.61以前には接続されません。 その理由は、古いサーババージョンは、バージョン6.73ではサポートされていない弱い形式の暗号を使うからです。

   1. OpenSSLバージョン1.0.1hでサポートされている強力な暗号リストを使用して、サーバ上のデフォルトのSSL暗号リストを上書きする。 上書きするには、「Components」ディレクトリと「Components for Processing Servers」ディレクトリにある「Communications.cfg」ファイルにキー「SSL暗号」を追加します。 例：`SSL Ciphers = string: !aNULL:AESGCM`

      >[!NOTE]
      >
      >キーがSSLポートと同じレベルに配置されていることを確認します。 詳しくは、[通信設定](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/config-settings/c-comm-cfg-stgs.html)を参照してください。

   1. 最新のtrust_ca_cert.pemファイルをサーバー6.61以前のサーバーに配置します。 この設定は、すべてのWorkstation 6.7xバージョンに適用されます。

Data Workbench 5.3 から 5.52 までについては、[アーカイブされているリリースノート](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html)を参照してください。
