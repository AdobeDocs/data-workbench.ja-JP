---
description: 変換フォルダーをアップグレードする手順です。
title: 変換のアップグレード
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 変換のアップグレード{#upgrading-transform}

変換フォルダーをアップグレードする手順です。

1. [!DNL Insight Server]リリースパッケージの[!DNL .zip]ファイルを開き、[!DNL .zip]ファイル内の[!DNL Profiles]フォルダーを開きます。
1. [!DNL Transform]フォルダーを[!DNL Insight Server]インストールディレクトリの[!DNL Profiles]フォルダーにコピーします。 これを行うと、既存の[!DNL Transform]フォルダーが上書きされます。
1. [!DNL Transform]プロファイルを継承する各プロファイルについて、 [!DNL profile.cfg]ファイルのDirectoriesベクトルに「Transform」エントリがあることを確認します。
プロファイルの同期後、データの再処理が開始されます。
