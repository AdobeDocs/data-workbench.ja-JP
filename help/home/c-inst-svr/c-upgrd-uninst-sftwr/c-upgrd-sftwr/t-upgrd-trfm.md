---
description: Transform フォルダーをアップグレードする手順です。
title: 変換のアップグレード
uuid: 26e567bc-7571-4317-b77c-2631a163a4b5
exl-id: b5e21862-caf1-42e4-9247-c870d7b3180e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---

# 変換のアップグレード{#upgrading-transform}

{{eol}}

Transform フォルダーをアップグレードする手順です。

1. を開きます。 [!DNL .zip] ファイル [!DNL Insight Server] パッケージをリリースし、 [!DNL Profiles] その中のフォルダ [!DNL .zip] ファイル。
1. を [!DNL Transform] フォルダーを [!DNL Profiles] の [!DNL Insight Server] インストールディレクトリ。 これを実行すると、既存の [!DNL Transform] フォルダー。
1. を継承する各プロファイルに対して、 [!DNL Transform] プロファイルで、 [!DNL profile.cfg] ファイルの Directories ベクトルには&quot;Transform&quot;エントリが含まれています。
データの再処理は、プロファイルの同期後に開始されます。
