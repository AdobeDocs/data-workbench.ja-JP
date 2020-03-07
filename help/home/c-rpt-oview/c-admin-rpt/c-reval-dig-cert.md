---
description: インストール後、アドビが発行したデジタル証明書は、Report Serverを実行するためのキーとして機能します。
solution: Analytics
title: デジタル証明書の再検証
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# デジタル証明書の再検証{#re-validating-the-digital-certificate}

インストール後、アドビが発行したデジタル証明書は、Report Serverを実行するためのキーとして機能します。

**推奨頻度：** 必要に応じて

正常に機能させるには、デジタル証明書が最新の状態である必要があります。

最新の状態を維持するには、デジタル証明書を定期的に再検証する必要があります（通常は30日ごとですが、アドビとの契約によって異なります）。 お使いのコンピューターがインターネットにアクセスできる場合、再検証プロセスは完全に透過的です。 [!DNL Report Server] が自動的にAdobe License Serverに接続され、必要に応じて証明書を再検証します。 お使いのコンピューターにインターネットアクセスがない場合は、Adobe License Serverから検証済みの新しい証明書をダウンロードし、デジタル証明書のダウンロードとインストールの手順に従ってコンピューターにインストールする必要があ [ります](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
