---
description: アクセス制御設定ファイルであるアクセス制御.cfgは、Insight Serverが受信アクセス制御の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与する接続グループを定義します。
title: アクセス制御の設定
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# アクセス制御の設定{#configuring-access-control}

アクセス制御設定ファイルであるアクセス制御.cfgは、Insight Serverが受信アクセス制御の証明書の属性（OU、CNなど）に基づいてファイルに対する権限を付与する接続グループを定義します。

**推奨頻度：** 必要に応じて

[!DNL Insight Server] には、接続のセキュリティを管理するための設定可能なアクセス制御グループが用意されて [!DNL Insight Server]います。アクセス制御グループは、[!DNL Insight]を介した管理機能の実行が許可されているユーザーを識別します。

[!DNL Insight Server]クラスターにマシンを追加する場合など、新しいユーザーや新しいマシンへのアクセスを提供する必要がある場合は、アクセス制御設定ファイルを編集します。
