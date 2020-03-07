---
description: Transformフォルダーをアップグレードする手順です。
solution: Insight
title: 変換のアップグレード
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 変換のアップグレード{#upgrading-transform}

Transformフォルダーをアップグレードする手順です。

1. リリースパッ [!DNL .zip] ケージのフ [!DNL Insight Server] ァイルを開き、そのファイ [!DNL Profiles] ル内のフォルダーを開 [!DNL .zip] きます。
1. インストールデ [!DNL Transform] ィレクトリ内の [!DNL Profiles] フォルダにフォルダをコ [!DNL Insight Server] ピーします。 この操作を行うと、既存のフォルダーが上書き [!DNL Transform] されます。
1. プロファイルを継承する各プロフ [!DNL Transform] ァイルに対して、ファイル [!DNL profile.cfg] のDirectoriesベクトルに「Transform」エントリがあることを確認します。
データの再処理は、プロファイルの同期後に開始されます。
