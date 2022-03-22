---
description: インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。
title: 電子証明書の再検証（概要）
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# 電子証明書の再検証{#re-validating-the-digital-certificate}

インストール後、Adobeが発行した電子証明書は、レポートサーバーを実行するためのキーとして機能します。

**Recommended Frequency:** As needed

正しく機能するには、電子証明書が最新である必要があります。

To remain current, your digital certificate must be re-validated on a regular basis (generally, every 30 days, but this can vary depending on your agreement with Adobe). コンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。[!DNL Report Server] connects automatically to the Adobe License Server and re-validates the certificate when necessary. コンピューターがインターネットにアクセスできない場合は、検証済みの新しい証明書をAdobeライセンスサーバーからダウンロードし、 [電子証明書のダウンロードとインストール](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
