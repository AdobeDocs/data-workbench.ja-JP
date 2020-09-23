---
description: Transformフォルダーをアップグレードする手順です。
solution: Analytics
title: 変換のアップグレード
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# 変換のアップグレード{#upgrading-transform}

Transformフォルダーをアップグレードする手順です。

1. リリースパッケージの [!DNL .zip] ファイルを開き、そのフ [!DNL Insight Server] ァイル内の [!DNL Profiles][!DNL .zip] フォルダーを開きます。
1. インストー [!DNL Transform] ルディレクトリ内の [!DNL Profiles] フォルダーにフォルダーをコピー [!DNL Insight Server] します。 これを行うと、既存の [!DNL Transform] フォルダーが上書きされます。
1. プロファイルを継承する各プロファイルについて、 [!DNL Transform] ベクトル内に「Transform」エントリがあることを [!DNL profile.cfg] 確認します。
データの再処理は、プロファイルの同期後に開始されます。
