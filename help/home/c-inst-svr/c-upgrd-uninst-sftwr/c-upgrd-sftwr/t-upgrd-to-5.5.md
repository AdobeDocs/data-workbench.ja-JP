---
description: Data Workbench6.1向けのサーバーコンポーネントを5.4インストールからアップグレードしています。
solution: Analytics
title: DWB Server 5.4から5.5へのアップグレード
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---


# DWB サーバーのアップグレード：5.4 から 5.5 へ{#dwb-server-upgrade-to}

Data Workbench6.1向けのサーバーコンポーネントを5.4インストールからアップグレードしています。

したがって、 [!DNL Insight] 5.4から5.5へのアップグレードは比較的簡単で [!DNL Insight] す。

次の手順を使用して、 [!DNL Insight] 5.3から [!DNL Insight] 5.5に直接アップグレードすることもできます。 「Insight 5.4から5.5への [アップグレード」節および「Insight 5.4から5.5への](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) アップグレード」節に記載されているすべてのアップグレードタスクを実行してください [](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 。

1. クラスター内のサーバー（サーバーを除く）すべてで [!DNL Insight Server] サービスを停止し [!DNL Insight Master Server]ます。

   1. 新しいファイル [!DNL ReportServer.exe] と [!DNL Insight.exe] ファイルをSoftware\Insightフォルダーにコピーします。

   1. クライアントが更新されたら、 [!DNL Insight] および [!DNL InsightServer.exe] フ [!DNL InsightServer64.exe] ァイルを\Binフォルダーにコピーします。

   1. to開始が表示され [!DNL Insight Master Server] るのを待ち、ビジュアライゼーションを介して実行されているバージョンを確認し [!DNL Connections] ます。

1. クライアント内のクラスター [!DNL Master Server] 上で、次の操作を [!DNL Insight] 行います。

   1. 既存の [!DNL Base] プロファイルのローカルコピーを作成し、名前を変更します（BaseBackupなど）。
   1. 新しい [!DNL Base] プロファイルーをプロファイルフォルダーにコピーします。
   1. Transformフォルダに対して、次の2つの手順を繰り返します。

1. サーバーパッケージのScriptsフォルダーを、サーバーインストールディレクトリ [!DNL Master Server] にコピーします。
1. ファイルを、のComponentsフォルダーにコピーし [!DNL Terrain Images.cfg.off][!DNL Master Server]ます。
   **クライアントソフトウェアを[!DNL Insight]5.4から5.5にアップグレードするには**

ファイルで、[ソフトウェアの更新]設定が[TRUE]に設定されていることを確認して [!DNL Insight.cfg] ください。
