---
description: Access Control設定ファイルAccess Control.cfgは、Insightサーバーが受信接続の証明書の属性（OU、CNなど）に基づいてファイルに権限を付与するアクセス制御グループを定義します。
title: アクセス制御の設定
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# アクセス制御の設定{#configuring-access-control}

Access Control設定ファイルAccess Control.cfgは、Insightサーバーが受信接続の証明書の属性（OU、CNなど）に基づいてファイルに権限を付与するアクセス制御グループを定義します。

**推奨される頻度：** 必要に応じて

[!DNL Insight Server] には、への接続のセキュリティを管理するための設定可能なアクセス制御グループが用意されてい [!DNL Insight Server]ます。アクセス制御グループは、[!DNL Insight]を介して管理機能を実行する権限を持つユーザーを特定します。

[!DNL Insight Server]クラスターにマシンを追加する場合など、新しいユーザーや新しいマシンへのアクセスを提供する必要がある場合は、アクセス制御設定ファイルを編集するだけです。
