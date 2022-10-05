---
description: インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。
title: 電子証明書の再検証（概要）
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# 電子証明書の再検証{#re-validating-the-digital-certificate}

{{eol}}

インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。

**推奨頻度：** 必要に応じて

正しく機能するには、電子証明書が最新である必要があります。

最新の状態に保つには、電子証明書を定期的に再検証する必要があります ( 通常、30 日ごとですが、Adobeとの契約によって異なります )。 コンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。[!DNL Report Server] は、必要に応じて、Adobeライセンスサーバーに自動的に接続し、証明書を再検証します。 コンピューターがインターネットにアクセスできない場合は、検証済みの新しい証明書をAdobeライセンスサーバーからダウンロードし、 [電子証明書のダウンロードとインストール](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
