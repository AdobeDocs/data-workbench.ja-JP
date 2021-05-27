---
description: Data Workbench6.1のサーバーコンポーネントを5.4からアップグレードします。
title: DWBサーバーの5.4から5.5へのアップグレード
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB サーバーのアップグレード：5.4 から 5.5 へ{#dwb-server-upgrade-to}

Data Workbench6.1のサーバーコンポーネントを5.4からアップグレードします。

したがって、[!DNL Insight] 5.4から[!DNL Insight] 5.5へのアップグレードは比較的簡単です。

次の手順を使用して、[!DNL Insight] 5.3から[!DNL Insight] 5.5に直接アップグレードすることもできます。 「[Insight 5.4から5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)へのアップグレード」および「[Insight 5.4から5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)へのアップグレード」に記載されているすべてのアップグレードタスクを実行してください。

1. [!DNL Insight Server]サービスは、[!DNL Insight Master Server]を除く、クラスター内のすべてのサーバーで停止します。

   1. 新しい[!DNL ReportServer.exe]ファイルと[!DNL Insight.exe]ファイルをSoftware\Insightフォルダーにコピーします。

   1. [!DNL Insight]クライアントが更新されたら、[!DNL InsightServer.exe]ファイルと[!DNL InsightServer64.exe]ファイルを\Binフォルダーにコピーします。

   1. [!DNL Insight Master Server]が開始するのを待ってから、[!DNL Connections]ビジュアライゼーションを使用して実行中のバージョンを確認します。

1. [!DNL Insight]クライアントでのクラスターの[!DNL Master Server]で、次の操作を実行します。

   1. 既存の[!DNL Base]プロファイルのローカルコピーを作成し、名前を変更します（例：BaseBackup）。
   1. 新しい[!DNL Base]プロファイルをProfilesフォルダーにコピーします。
   1. 変換フォルダーに対して、次の2つの手順を繰り返します。

1. サーバーパッケージのScriptsフォルダーを[!DNL Master Server]のServerインストールディレクトリにコピーします。
1. [!DNL Terrain Images.cfg.off]ファイルを[!DNL Master Server]のComponentsフォルダーにコピーします。
   **クライアントソフトウェアを [!DNL Insight] 5.4から5.5にアップグレードするには**

[!DNL Insight.cfg]ファイルで、「ソフトウェアの更新」設定がTRUEに設定されていることを確認します。
