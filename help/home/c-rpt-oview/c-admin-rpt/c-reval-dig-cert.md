---
description: インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。
title: 電子証明書の再検証
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 13%

---

# 電子証明書の再検証{#re-validating-the-digital-certificate}

インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。

**推奨される頻度：** 必要に応じて

正しく機能させるには、電子証明書が最新である必要があります。

最新の状態に保つには、デジタル証明書を定期的に再検証する必要があります(通常、30日ごとに検証されますが、Adobeとの契約によって異なります)。 コンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。[!DNL Report Server] は、自動的にAdobeライセンスサーバーに接続し、必要に応じて証明書を再検証します。お使いのコンピューターにインターネットアクセスがない場合は、検証済みの新しい証明書をAdobeライセンスサーバーからダウンロードし、[デジタル証明書](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)のダウンロードとインストールの手順に従って、お使いのコンピューターにインストールします。
