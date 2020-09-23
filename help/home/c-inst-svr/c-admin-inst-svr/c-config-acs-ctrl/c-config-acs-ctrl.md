---
description: アクセス制御設定ファイルであるアクセス制御.cfgは、Insight Serverが受信アクセス制御の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与する接続グループを定義します。
solution: Analytics
title: アクセス制御の設定
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---


# アクセス制御の設定{#configuring-access-control}

アクセス制御設定ファイルであるアクセス制御.cfgは、Insight Serverが受信アクセス制御の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与する接続グループを定義します。

**推奨頻度：** 必要に応じて

[!DNL Insight Server] には、接続のセキュリティを管理するための設定可能なアクセス制御グループが用意されて [!DNL Insight Server]います。 アクセス制御グループは、を通じて管理機能を実行できるユーザーを識別 [!DNL Insight]します。

マシンをクラスターに追加する場合など、新しいユーザーまたは新しいマシンへのアクセスを提供する必要がある場合は、アクセス制御設定ファイルを編集するだけです。 [!DNL Insight Server]
