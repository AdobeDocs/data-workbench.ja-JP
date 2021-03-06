---
description: 事前に作成された5つのアクセス制御グループを使用できますが、必要に応じて追加のグループを作成および管理できます。
title: アクセス制御グループについて
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# アクセス制御グループについて{#understanding-access-control-groups}

事前に作成された5つのアクセス制御グループを使用できますが、必要に応じて追加のグループを作成および管理できます。

各アクセス制御グループのメンバー、および各グループが読み取り専用または読み取り/書き込みアクセス権を持つディレクトリを定義できます。

事前定義済みのグループは、次のように定義されます。

| グループ | 説明 |
|---|---|
| 管理者 | すべてのディレクトリとファイルへのアクセスを許可します。 デフォルトのIPアドレスは127.0.0.1（ローカルホスト）です。 |
| センサー | [!DNL Sensor]がデータの送信に使用するファイルにのみアクセスできます。 |
| ユーザー | [!DNL Insight]ユーザーが基本的な分析タスクを実行する際に必要な要素に対する読み取り専用アクセスを許可します。 |
| パワーユーザー | [!DNL Insight]ユーザーが基本的な分析タスクを実行するのに必要な要素に対する読み取り専用アクセス、およびプロファイルを変更するための[!DNL Profiles]フォルダーへの読み取り/書き込みアクセスを許可します。 |
| クラスタサーバ | クラスターサーバーとして指定された[!DNL Insight Servers]へのアクセスを許可します。 |
| レポートサーバー | [!DNL Insight Server]に接続する[!DNL Report]マシンへのアクセスを許可します。 |

アクセス制御グループのメンバーは、IPアドレスまたはSSL証明書情報を使用して定義されます。

SSL証明書が使用できない場合は、IPアドレスを使用してグループメンバーを定義できます。 [!DNL Insight]の通常のインストールにはSSL証明書が含まれますが、[!DNL Sensor(s)]の証明書の使用はオプションです。 [!DNL Insight Server]の場合、クラスターサーバーはSSL証明書ではなくIPアドレスを使用して定義されます。

グループメンバーを定義するには、次のコードを使用できます。

| アクセスタイプコード | 定義 |
|---|---|
| O | 組織 |
| CN | 共通名 |
| L | 市区町村 |
| ST | 都道府県 |
| C | 国 |
| OU | 組織単位 |
| 電子メール | 電子メール住所 |
