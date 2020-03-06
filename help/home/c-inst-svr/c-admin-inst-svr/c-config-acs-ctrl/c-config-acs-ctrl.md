---
description: アクセス制御設定ファイルAccess Control.cfgは、Insight Serverが受信接続の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与するアクセス制御グループを定義します。
solution: Insight
title: アクセス制御の設定
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# アクセス制御の設定{#configuring-access-control}

アクセス制御設定ファイルAccess Control.cfgは、Insight Serverが受信接続の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与するアクセス制御グループを定義します。

**推奨頻度：** 必要に応じて

[!DNL Insight Server] は、接続のセキュリティを管理するための設定可能なアクセス制御グループを提供しま [!DNL Insight Server]す。 アクセス制御グループは、を通じて管理機能の実行を許可されるユーザーを識別しま [!DNL Insight]す。

新しいユーザーや新しいマシンへのアクセスを提供する必要がある場合（例えば、マシンをクラスターに追加する場合）は、単にア [!DNL Insight Server] クセス制御設定ファイルを編集します。
