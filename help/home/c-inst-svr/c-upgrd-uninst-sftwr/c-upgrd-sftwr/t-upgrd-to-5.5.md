---
description: Data Workbench6.1 のサーバーコンポーネントを 5.4 のインストールからアップグレードします。
title: DWB サーバーの 5.4 から 5.5 へのアップグレード
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB サーバーのアップグレード：5.4 から 5.5 へ{#dwb-server-upgrade-to}

{{eol}}

Data Workbench6.1 のサーバーコンポーネントを 5.4 のインストールからアップグレードします。

その結果、 [!DNL Insight] 5.4～ [!DNL Insight] 5.5 は比較的単純です。

また、 [!DNL Insight] 5.3～ [!DNL Insight] 5.5 を使用します。 必ず、 [Insight 5.4 から 5.5 へのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) セクションおよび [Insight 5.4 から 5.5 へのアップグレード](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 」セクションに入力します。

1. を停止します。 [!DNL Insight Server] クラスタ内のすべてのサーバー上のサービス ( [!DNL Insight Master Server].

   1. 新しい [!DNL ReportServer.exe] および [!DNL Insight.exe] ファイルを Software\Insight フォルダーに保存します。

   1. 次の期間の後 [!DNL Insight] クライアントが更新されました。 [!DNL InsightServer.exe] および [!DNL InsightServer64.exe] ファイルを\Bin フォルダーに格納します。

   1. 待機： [!DNL Insight Master Server] を起動し、 [!DNL Connections] ビジュアライゼーション。

1. クラスターの [!DNL Master Server] 内 [!DNL Insight] クライアント：

   1. 既存のコピーをローカルに作成 [!DNL Base] プロファイルを作成し、名前を変更します（例：BaseBackup）。
   1. 新しい [!DNL Base] プロファイルを Profiles フォルダーに追加します。
   1. Transform フォルダに対して、次の 2 つの手順を繰り返します。

1. サーバーパッケージから [!DNL Master Server] を Server インストールディレクトリに追加します。
1. を [!DNL Terrain Images.cfg.off] ファイルを [!DNL Master Server].
   **クライアントソフトウェアをからアップグレードするには [!DNL Insight] 5.4～5.5**

内 [!DNL Insight.cfg] ファイルに含める場合は、[ ソフトウェアの更新 ] の設定が [TRUE] に設定されていることを確認します。
