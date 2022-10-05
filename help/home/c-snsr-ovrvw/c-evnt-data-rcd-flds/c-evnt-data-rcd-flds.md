---
description: ログ（.vsl）ファイルには、Sensor によってサーバーから収集され、Data Workbench サーバーがデータセット構築プロセスで使用するイベントデータのフィールドが格納されます。
title: イベントデータレコードフィールド（.vsl ファイル）
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 54%

---

# イベントデータレコードフィールド{#event-data-record-fields}

{{eol}}

ログ（.vsl）ファイルには、Sensor によってサーバーから収集され、Data Workbench サーバーがデータセット構築プロセスで使用するイベントデータのフィールドが格納されます。

フィールドの名前は、通常、W3C 拡張ログファイル形式の命名規則に従います。 多くのフィールドには、その情報の取得元を表すプレフィックスが付いています。

* 「cs」は、クライアントからサーバへの通信を示します。
* 「sc」は、サーバーからクライアントへの通信を示します
* 「s」は、サーバからの情報を示します。
* 「c」はクライアントからの情報を示します
* 「x」は、Adobe製品によって作成された情報を示します
