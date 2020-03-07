---
description: Data Workbench 6.1のサーバーコンポーネントを5.4のインストールからアップグレードする。
solution: Insight
title: DWB Server 5.4から5.5へのアップグレード
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWBサーバーのアップグレード：5.4 ～ 5.5{#dwb-server-upgrade-to}

Data Workbench 6.1のサーバーコンポーネントを5.4のインストールからアップグレードする。

したがって、 [!DNL Insight] 5.4から5.5へのアッ [!DNL Insight] プグレードは比較的簡単です。

次の手順を使用して、 [!DNL Insight] 5.3から5.5 [!DNL Insight] に直接アップグレードすることもできます。 「 [Insight 5.4から5.5へのアップグレード」および「](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) Insight 5.4から5.5へのアップグレード」に記載されているすべてのアップグレードタスクを [必ず実行してください](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 。

1. クラスター内 [!DNL Insight Server] のサーバー（サーバーを除く）のすべてでサービスを停止しま [!DNL Insight Master Server]す。

   1. 新しいファイルと [!DNL ReportServer.exe] ファイル [!DNL Insight.exe] をSoftware\Insightフォルダーにコピーします。

   1. クライアント [!DNL Insight] の更新後、ファイルとフ [!DNL InsightServer.exe] ァイルを\Bin [!DNL InsightServer64.exe] フォルダーにコピーします。

   1. が起動するのを待 [!DNL Insight Master Server] ってから、ビジュアライゼーションを介して実行中のバージョンを確認 [!DNL Connections] します。

1. クライアント内のクラ [!DNL Master Server] スター [!DNL Insight] 上：

   1. 既存のプロファイルのローカルコピー [!DNL Base] を作成し、名前を変更します（例：BaseBackup）。
   1. 新しいプロファイルをProfiles [!DNL Base] フォルダーにコピーします。
   1. Transformフォルダに対して、次の2つの手順を繰り返します。

1. サーバーパッケージのScriptsフォルダーを、サーバーインストールディレ [!DNL Master Server] クトリのにコピーします。
1. ファイルを、 [!DNL Terrain Images.cfg.off] のComponentsフォルダーにコピーしま [!DNL Master Server]す。
   **クライアントソフトウェアを[!DNL Insight]5.4から5.5にアップグレードするには**

ファイル内 [!DNL Insight.cfg] で、[ソフトウェアの更新]の設定が[TRUE]に設定されていることを確認します。
