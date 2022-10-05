---
description: Access Control 設定ファイル Access Control.cfg は、受信接続の証明書の属性（OU、CN など）に基づいて、Insight サーバーがファイルに対して権限を付与するアクセス制御グループを定義します。
title: アクセス制御の設定
uuid: e0206b43-3c8c-48ec-b663-814f5b663b96
exl-id: 2836c907-fc74-4d35-badc-b8f06cd6989f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 4%

---

# アクセス制御の設定{#configuring-access-control}

{{eol}}

Access Control 設定ファイル Access Control.cfg は、受信接続の証明書の属性（OU、CN など）に基づいて、Insight サーバーがファイルに対して権限を付与するアクセス制御グループを定義します。

**推奨頻度：** 必要に応じて

[!DNL Insight Server] 接続のセキュリティを管理するための設定可能なアクセス制御グループを提供 [!DNL Insight Server]. アクセス制御グループは、を通じて管理機能を実行する権限を持つユーザーを特定します。 [!DNL Insight].

新しいユーザーや新しいマシンへのアクセスを提供する必要がある場合 ( マシンを [!DNL Insight Server] クラスターを使用する場合は、Access Control 設定ファイルを編集するだけです。
