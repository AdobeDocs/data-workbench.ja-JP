---
description: Data Workbench6.1向けのサーバーコンポーネントを5.4インストールからアップグレードしています。
title: DWB Server 5.4から5.5へのアップグレード
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB サーバーのアップグレード：5.4 から 5.5 へ{#dwb-server-upgrade-to}

Data Workbench6.1向けのサーバーコンポーネントを5.4インストールからアップグレードしています。

したがって、[!DNL Insight] 5.4から[!DNL Insight] 5.5へのアップグレードは比較的簡単です。

また、次の手順を使用して、[!DNL Insight] 5.3から[!DNL Insight] 5.5に直接アップグレードすることもできます。 「[Insight 5.4から5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)へのアップグレード」および「[Insight 5.4から5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)へのアップグレード」に記載されているすべてのアップグレードタスクを実行してください。

1. [!DNL Insight Server]サービスを、クラスター内の[!DNL Insight Master Server]を除くすべてのサーバーで停止します。

   1. 新しい[!DNL ReportServer.exe]ファイルと[!DNL Insight.exe]ファイルをSoftware\Insightフォルダーにコピーします。

   1. [!DNL Insight]クライアントの更新後、[!DNL InsightServer.exe]ファイルと[!DNL InsightServer64.exe]ファイルを\Binフォルダーにコピーします。

   1. [!DNL Insight Master Server]が開始するのを待ち、[!DNL Connections]ビジュアライゼーションで実行中のバージョンを確認します。

1. クラスターの[!DNL Master Server] （[!DNL Insight]クライアント内）:

   1. 既存の[!DNL Base]プロファイルのローカルコピーを作成し、名前を変更します（例：BaseBackup）。
   1. 新しい[!DNL Base]プロファイルーをプロファイルフォルダーにコピーします。
   1. Transformフォルダに対して、次の2つの手順を繰り返します。

1. サーバーパッケージのScriptsフォルダーを[!DNL Master Server]にコピーして、サーバーインストールディレクトリに置きます。
1. [!DNL Terrain Images.cfg.off]ファイルを[!DNL Master Server]のComponentsフォルダーにコピーします。
   **クライアントソフトウェアを [!DNL Insight] 5.4から5.5にアップグレードするには**

[!DNL Insight.cfg]ファイルで、「ソフトウェアの更新」設定が「TRUE」に設定されていることを確認します。
